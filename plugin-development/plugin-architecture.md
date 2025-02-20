# Plugin Architecture Guide

## Overview

FouzderIT Business Suite uses a modular plugin architecture that allows developers to extend functionality while maintaining core system stability. This guide covers the architectural principles, component structure, and best practices for plugin development.

## Plugin Structure

### Basic Plugin Directory Structure

    apps/
    └── your_plugin/
        ├── manifest.php
        ├── boot.php
        ├── app.php
        ├── install.php
        ├── uninstall.php
        ├── models/
        │   └── CustomModel.php
        ├── views/
        │   ├── list.tpl
        │   ├── add.tpl
        │   └── edit.tpl
        ├── controllers/
        │   └── CustomController.php
        └── assets/
            ├── js/
            ├── css/
            └── img/
    

### Core Files Explanation

#### 1\. Manifest File

    <?php
    // manifest.php
    $plugin = [
        'name' => 'Your Plugin Name',
        'author' => 'Your Name',
        'version' => '1.0.0',
        'description' => 'Plugin description',
        'url' => 'https://your-website.com',
        'priority' => 1,
        'build' => 1000,
        'requires' => [
            'core_version' => '3.0.0',
            'php_version' => '8.2.0'
        ]
    ];
    

#### 2\. Boot File

    <?php
    // boot.php - Executes when system boots
    // Register menus, hooks, and initialization code
    
    // Add admin menu
    $admin_submenu = [
        [
            'name' => 'Add New',
            'link' => U.'your_plugin/app/add/'
        ],
        [
            'name' => 'List All',
            'link' => U.'your_plugin/app/list/'
        ]
    ];
    
    add_menu_admin('Plugin Name', U.'your_plugin/app', 'plugin_icon', 'fa fa-plug', 2, $admin_submenu);
    
    // Register hooks
    add_hook('admin_dashboard', 1, function() {
        // Dashboard widget code
    });
    

#### 3\. Installation Handler

    <?php
    // install.php - Executes during plugin installation
    
    // Create database tables
    $table = new Schema('plugin_table');
    $table->add('title', 'varchar', 200);
    $table->add('description', 'text');
    $table->add('created_at', 'datetime');
    $table->add('updated_at', 'datetime');
    $table->save();
    
    // Add configuration
    add_option('plugin_setting_key', 'default_value');
    

#### 4\. Uninstallation Handler

    <?php
    // uninstall.php - Cleanup when plugin is uninstalled
    
    // Remove tables
    $table = new Schema('plugin_table');
    $table->drop();
    
    // Remove configuration
    delete_option('plugin_setting_key');
    

## Plugin Components

### 1\. Models

    <?php
    // models/CustomModel.php
    use Illuminate\Database\Eloquent\Model;
    
    class CustomModel extends Model
    {
        protected $table = 'plugin_table';
        protected $fillable = ['title', 'description'];
        
        // Define relationships
        public function relatedModel()
        {
            return $this->hasMany('RelatedModel');
        }
    }
    

### 2\. Views

    {* views/list.tpl *}
    {block name="content"}
    <div class="panel panel-default">
        <div class="panel-heading">
            <h3 class="panel-title">{$_L['Items']}</h3>
        </div>
        <div class="panel-body">
            <table class="table table-bordered">
                <thead>
                    <tr>
                        <th>{$_L['Title']}</th>
                        <th>{$_L['Description']}</th>
                        <th>{$_L['Actions']}</th>
                    </tr>
                </thead>
                <tbody>
                    {foreach $items as $item}
                        <tr>
                            <td>{$item->title}</td>
                            <td>{$item->description}</td>
                            <td>
                                <a href="{$_url}your_plugin/app/edit/{$item->id}" 
                                   class="btn btn-primary btn-xs">
                                    {$_L['Edit']}
                                </a>
                            </td>
                        </tr>
                    {/foreach}
                </tbody>
            </table>
        </div>
    </div>
    {/block}
    

### 3\. Controllers

    <?php
    // app.php - Main controller
    require 'models/CustomModel.php';
    
    $action = route(2, 'list');
    _auth();
    
    $ui->assign('_application_menu', 'your_plugin');
    $ui->assign('_title', 'Your Plugin');
    
    switch ($action) {
        case 'list':
            $items = CustomModel::orderBy('id', 'desc')->get();
            
            view('app_wrapper', [
                '_include' => 'list',
                'items' => $items
            ]);
            break;
            
        case 'add':
            view('app_wrapper', [
                '_include' => 'add'
            ]);
            break;
            
        case 'save':
            $validator = new Validator;
            $validation = $validator->make($_POST, [
                'title' => 'required|max:200',
                'description' => 'required'
            ]);
            
            if ($validation->fails()) {
                r2(U.'your_plugin/app/add', 'e', $validation->errors()[0]);
            }
            
            $item = new CustomModel;
            $item->title = _post('title');
            $item->description = _post('description');
            $item->save();
            
            r2(U.'your_plugin/app/list', 's', 'Item added successfully');
            break;
    }
    

## Hook System

### Available Hook Points

    // Register hooks in boot.php
    add_hook('admin_dashboard', 1, function() {
        // Dashboard content
    });
    
    add_hook('client_dashboard', 1, function() {
        // Client dashboard content
    });
    
    add_hook('invoice_created', 1, function($invoice) {
        // Handle new invoice
    });
    
    add_hook('payment_received', 1, function($payment) {
        // Handle payment
    });
    

### Custom Hook Points

    // Define hook point
    $result = run_hook('custom_hook_name', $data);
    
    // Register handler
    add_hook('custom_hook_name', 1, function($data) {
        // Process data
        return $modified_data;
    });
    

## Database Integration

### Schema Management

    // Create table with relationships
    $table = new Schema('plugin_items');
    $table->add('title', 'varchar', 200);
    $table->add('user_id', 'int', 11);
    $table->add_foreign_key('user_id', 'sys_users', 'id', 'CASCADE', 'CASCADE');
    $table->save();
    

### Query Building

    // Using Query Builder
    $items = DB::table('plugin_items')
        ->where('user_id', $user_id)
        ->orderBy('created_at', 'desc')
        ->get();
    
    // Using Eloquent
    $items = CustomModel::with('relatedModel')
        ->where('status', 'active')
        ->get();
    

## Security Best Practices

### 1\. Input Validation

    // Validate user input
    $validator = new Validator;
    $validation = $validator->make($_POST, [
        'email' => 'required|email',
        'amount' => 'required|numeric|min:0'
    ]);
    
    if ($validation->fails()) {
        r2(U.'your_plugin/app/add', 'e', $validation->errors()[0]);
    }
    

### 2\. Access Control

    // Check permissions
    if (!has_access($user->roleid, 'your_plugin', 'edit')) {
        r2(U.'dashboard', 'e', 'Access Denied');
    }
    
    // Verify CSRF token
    if (!verify_csrf_token()) {
        r2(U.'dashboard', 'e', 'Invalid Token');
    }
    

### 3\. SQL Injection Prevention

    // Use parameterized queries
    $result = DB::select("SELECT * FROM plugin_items WHERE id = ?", [$id]);
    
    // Use Query Builder
    $result = DB::table('plugin_items')
        ->where('id', $id)
        ->first();
    

## Plugin Settings

### Configuration Management

    // Save settings
    add_option('plugin_setting', $value);
    
    // Retrieve settings
    $setting = get_option('plugin_setting');
    
    // Update settings
    update_option('plugin_setting', $new_value);
    
    // Delete settings
    delete_option('plugin_setting');
    

## Asset Management

### Including Resources

    // Add CSS
    add_css('apps/your_plugin/assets/css/style.css');
    
    // Add JavaScript
    add_js('apps/your_plugin/assets/js/script.js');
    
    // Add inline script
    add_js_script('
        $(document).ready(function() {
            // Your code here
        });
    ');
    

## Internationalization

### Language Support

    // Add language strings
    $_L['plugin_string'] = 'Translated Text';
    
    // Use in templates
    {$_L['plugin_string']}
    
    // Use in PHP
    _L('plugin_string');
    

## Error Handling

### Proper Exception Handling

    try {
        // Plugin operation
        $result = perform_operation();
        
        if (!$result) {
            throw new Exception('Operation failed');
        }
    } catch (Exception $e) {
        _log($e->getMessage());
        r2(U.'your_plugin/app/list', 'e', $e->getMessage());
    }