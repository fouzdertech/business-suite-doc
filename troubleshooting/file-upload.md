# Understanding File Upload Limits

File uploads in CloudOnex Business Suite are subject to several PHP configuration limits that may need to be adjusted depending on your needs:

-   `upload_max_filesize`: Maximum size of individual uploaded files
-   `post_max_size`: Maximum size of POST data (should be larger than upload\_max\_filesize)
-   `memory_limit`: Maximum memory a script can consume
-   `max_execution_time`: Maximum time in seconds a script can run

## Adjusting Limits in cPanel & Shared Hosting

If your hosting uses cPanel, you can easily modify PHP settings:

1.  Log in to your cPanel account
2.  Navigate to **Software** → **Select PHP Version** or **MultiPHP INI Editor**
3.  Select your domain if prompted
4.  Look for the following directives and adjust their values:
    
        upload_max_filesize = 64M
        post_max_size = 64M
        memory_limit = 256M
        max_execution_time = 300
        
    
5.  Click **Apply Changes** or **Save**

## For VPS or Cloud Server: Modifying PHP.ini Settings

If you have direct access to your server's PHP configuration:

1.  Locate your `php.ini` file (common locations):
    
    -   Linux: `/etc/php.ini` or `/etc/php/[version]/apache2/php.ini`
    -   Windows: `C:\php\php.ini`
2.  Add or modify these lines:
    
        ; Increase file upload size limit to 64MB
        upload_max_filesize = 64M
        
        ; Increase POST size limit to 64MB (should be equal or larger than upload_max_filesize)
        post_max_size = 64M
        
        ; Increase memory limit to 256MB
        memory_limit = 256M
        
        ; Increase max execution time to 5 minutes
        max_execution_time = 300
        
    
3.  Save the file and restart your web server:
    
        # Apache on Linux
        sudo service apache2 restart
        
        # Nginx on Linux
        sudo service nginx restart
        
        # XAMPP on Windows
        restart Apache from XAMPP Control Panel
        
    

## Using .htaccess Method

If you don't have access to `php.ini` or cPanel, you can try using `.htaccess`:

1.  Create or edit `.htaccess` in your website's root directory
2.  Add these lines:
    
        php_value upload_max_filesize 64M
        php_value post_max_size 64M
        php_value memory_limit 256M
        php_value max_execution_time 300
        
    

## Using ini\_set() Method

In some cases, you might need to set these values programmatically:

    ini_set('upload_max_filesize', '64M');
    ini_set('post_max_size', '64M');
    ini_set('memory_limit', '256M');
    ini_set('max_execution_time', 300);
    

Note: Some settings cannot be changed using `ini_set()` and must be set in `php.ini` or through server configuration.

## Verifying Changes

To verify your changes have taken effect:

1.  Create a PHP info file:
    
        <?php phpinfo(); ?>
        
    
2.  Upload it to your server as `info.php`
3.  Access it through your browser
4.  Search for the directives you modified
5.  **Important**: Delete this file after verification for security reasons

## Common Issues and Solutions

1.  **Changes Not Taking Effect**:
    
    -   Ensure you're editing the correct `php.ini` file
    -   Restart your web server after changes
    -   Check if your hosting provider allows these changes
2.  **Server Restrictions**:
    
    -   Some hosting providers may have hard limits
    -   Contact your hosting provider for assistance
    -   Consider upgrading your hosting plan if needed
3.  **Memory Errors During Upload**:
    
    -   Increase both `memory_limit` and `max_execution_time`
    -   Consider optimizing file sizes before upload
    -   Implement chunked file uploads for very large files