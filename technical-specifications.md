# Technical Specifications

## Framework Architecture

FouzderIT Business Suite is built on a custom framework optimized for business applications. Rather than using a single monolithic framework, it employs a modular approach incorporating best-in-class libraries for specific functionalities.

### Core Components

#### 1\. Database Layer

-   **Primary ORM**: Laravel Eloquent
-   **Usage Example**:

    use Illuminate\Database\Eloquent\Model;
    
    class Customer extends Model
    {
        protected $table = 'sys_customers';
        protected $fillable = ['name', 'email', 'phone'];
        
        public function invoices()
        {
            return $this->hasMany('Invoice');
        }
    }
    

#### 2\. Caching System

-   **Library**: illuminate/cache
-   **Features**:
    -   Multiple cache drivers support
    -   Automatic cache invalidation
    -   Tag-based caching

    // Cache configuration
    $cache = new Illuminate\Cache\Repository($store);
    $cache->put('key', 'value', 60); // Store for 60 minutes
    

#### 3\. File System

-   **Library**: illuminate/filesystem
-   **Capabilities**:
    -   File and directory manipulation
    -   Cloud storage integration
    -   Stream wrappers

    use Illuminate\Filesystem\Filesystem;
    $files = new Filesystem;
    $files->put('path/to/file.txt', 'Content');
    

#### 4\. Console & Automation

-   **Framework**: symfony/console
-   **Features**:
    -   Command-line interface
    -   Scheduled tasks
    -   Background jobs

    use Symfony\Component\Console\Command\Command;
    
    class DataSyncCommand extends Command
    {
        protected function configure()
        {
            $this->setName('app:sync-data')
                 ->setDescription('Synchronize data');
        }
    }
    

#### 5\. Template Engine

-   **Base**: Smarty (Customized)
-   **Extensions**: Custom tags and modifiers

    {* Template Example *}
    {block name="content"}
        <div class="panel">
            <h3>{$title}</h3>
            {foreach $items as $item}
                <div>{$item.name}</div>
            {/foreach}
        </div>
    {/block}
    

#### 6\. Routing System

-   **Type**: Custom Implementation
-   **Features**:
    -   URL rewrite optional
    -   Subfolder installation support
    -   Automatic route resolution

    // Example URL structure
    // With URL rewrite: /customers/view/123
    // Without URL rewrite: ?ng=customers/view/123
    
    $action = route(2); // Gets the action segment
    $id = route(3);     // Gets the ID segment
    

## System Requirements

### Server Requirements

-   PHP 8.2 or higher
-   Required PHP Extensions:
    -   curl
    -   json
    -   mysqli
    -   pdo
    -   zip
    -   mbstring
    -   gd

### Database Requirements

-   MySQL 5.7+ or MariaDB 10.2+
-   InnoDB storage engine
-   UTF8mb4 character set support

## Dependencies

### Core Libraries

    {
        "illuminate/database": "*",
        "illuminate/cache": "*",
        "illuminate/filesystem": "*",
        "symfony/console": "*",
        "smarty/smarty": "*"
    }
    

### Additional Components

-   **PDF Generation**: mpdf/mpdf ^8.0
-   **Email Handling**: phpmailer/phpmailer ^6.6
-   **Data Validation**: rakit/validation ^1.4
-   **Date/Time**: nesbot/carbon ^2.62
-   **HTTP Client**: guzzlehttp/guzzle ^7.5

## Application Structure

    /
    ├── apps/           # Plugin directory
    ├── storage/        # File storage
    ├── system/
    │   ├── autoload/  # Autoloader classes
    │   ├── models/    # Core models
    │   ├── controllers/
    │   └── lib/       # Core libraries
    ├── ui/
    │   └── theme/     # Theme files
    └── vendor/        # Composer dependencies
    

## Autoloading

### PSR-0 Autoloading

    "autoload": {
        "psr-0": {
            "": "system/autoload/"
        }
    }
    

### PSR-4 Autoloading

    "autoload": {
        "psr-4": {
            "": "system/models/"
        }
    }
    

## Performance Optimization

### Caching Configuration

    // Production cache settings
    define('CACHE_DRIVER', 'file'); // Options: file, redis, memcached
    define('CACHE_PREFIX', 'clx_');
    

### Database Optimization

    // Query caching
    DB::enableQueryLog();
    DB::connection()->enableQueryLog();
    

## Security Features

### Input Validation

    
    $validator = new Validator;
    $validation = $validator->make($data, [
        'email' => 'required|email',
        'amount' => 'required|numeric'
    ]);
    

### XSS Protection

-   HTMLPurifier integration
-   Automatic input sanitization

    use HTMLPurifier;
    $config = HTMLPurifier_Config::createDefault();
    $purifier = new HTMLPurifier($config);
    $clean_html = $purifier->purify($dirty_html);
    

### Email Integration

    use PHPMailer\PHPMailer\PHPMailer;
    
    $mail = new PHPMailer(true);
    $mail->isSMTP();
    $mail->Host = SMTP_HOST;
    $mail->SMTPAuth = true;
    

## Development Tools

### Debug Mode

    // Enable development mode
    define('APP_STAGE', 'Dev');
    
    // Debug helper
    function _debug($data) {
        if(APP_STAGE == 'Dev') {
            var_dump($data);
        }
    }