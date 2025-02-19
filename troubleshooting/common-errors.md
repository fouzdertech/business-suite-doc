# Common Errors and Solutions Guide

## Quick Diagnostic Steps

Before diving into specific errors, try these initial diagnostic steps:

1.  Enable Developer Mode

    // Edit system/config.php
    define('APP_STAGE', 'Dev');
    

2.  Check PHP error logs
3.  Verify system requirements
4.  Clear browser cache

## Common Error Categories

### 1\. Installation Errors

#### Blank Screen During Installation

**Symptoms:**

-   White screen
-   No error message
-   Installation doesn't proceed

**Solutions:**

1.  Verify PHP Version
    
        php -v  # Should show PHP 8.3 or higher
        
    
2.  Check PHP Extensions
    
        php -m  # Should list: mbstring, PDO, GD, JSON
        
    
3.  Update PHP Memory Limit
    
        memory_limit = 256M
        
    

#### Database Connection Failed

**Symptoms:**

-   "Could not connect to database" error
-   Database configuration errors

**Solutions:**

1.  Verify Database Credentials
    
    -   Check username/password
    -   Confirm database exists
    
        SHOW DATABASES;
        
    
2.  Test MySQL Connection
    
        mysql -u username -p database_name
        
    
3.  Check MySQL User Privileges
    
        GRANT ALL PRIVILEGES ON database_name.* TO 'username'@'localhost';
        FLUSH PRIVILEGES;
        
    

### 2\. Login Issues

#### Cannot Login to Admin Panel

**Symptoms:**

-   Login credentials not accepted
-   Redirect loops
-   Session errors

**Solutions:**

If you have forgotten the admin Password, you should be able to reset it using Forgot Password link available in the login page. But if it does not work, for example sending email is disable in your server, your email is mis configured, you may not receive email to reset password. In that case, you can reset password directly from database.

The name of the users table is sys\_users  
Open the sys\_users table with any mysql tool for example phpMyAdmin and edit the password field for specific user with the following contents-

`$1$WN..nD2.$Vo9niDl/fUf0VhheEjmHe/`

By doing this, your password will be set to- **123456**  
Change your password immediately after login.

### 3\. Payment Gateway Errors

#### PayPal Integration Issues

**Symptoms:**

-   Payment not processed
-   API connection errors
-   IPN not working

**Solutions:**

1.  Verify API Credentials
    
    -   Check API keys
    -   Confirm PayPal email
    -   Verify IPN URL
2.  Enable PayPal Logging
    
        // Enable in system/config.php
        define('PAYPAL_DEBUG', true);
        
    
3.  Check SSL Certificate
    
    -   Verify SSL is valid
    -   Check certificate expiration
    -   Confirm proper installation

### 4\. Invoice Generation Problems

#### PDF Generation Fails

**Symptoms:**

-   Blank PDFs
-   Error when generating invoices
-   Missing PDF attachments

**Solutions:**

1.  Check Directory Permissions
    
        chmod 755 storage/temp
        chown www-data:www-data storage/temp
        
    
2.  Verify PHP Extensions
    
        php -m | grep -E "gd|mbstring"
        
    
3.  Test PDF Generation
    
        // Add to test.php
        <?php
        require_once 'vendor/autoload.php';
        use Mpdf\Mpdf;
        $mpdf = new Mpdf();
        $mpdf->WriteHTML('<h1>Test PDF</h1>');
        $mpdf->Output();
        
    

### 5\. Email Configuration Issues

#### Emails Not Sending

**Symptoms:**

-   Emails not received
-   SMTP connection errors
-   Timeout errors

**Solutions:**

1.  Verify SMTP Settings
    
        // Test SMTP connection
        $mail = new PHPMailer(true);
        $mail->SMTPDebug = 2;
        $mail->isSMTP();
        // Add your SMTP settings
        $mail->send();
        
    
2.  Check Email Logs
    
    -   Navigate to Utilities → Email Logs
    -   Look for specific error messages
3.  Test Alternative Drivers
    
        // Try PHP mail() function
        define('EMAIL_DRIVER', 'mail');
        
    

### 6\. Performance Issues

#### Slow System Response

**Symptoms:**

-   Pages load slowly
-   Time-out errors
-   High server load

**Solutions:**

1.  Enable Caching
    
        // In system/config.php
        define('CACHE_DRIVER', 'file');
        
    
2.  Optimize Database
    
        OPTIMIZE TABLE sys_invoices, sys_transactions, sys_users;
        
    
3.  Check Server Resources
    
        # Check CPU usage
        top
        # Check disk space
        df -h
        # Check memory usage
        free -m
        
    

### 7\. Plugin-Related Issues

#### Plugin Installation Fails

**Symptoms:**

-   Installation errors
-   Plugins not appearing
-   Functionality not working

**Solutions:**

1.  Check Plugin Compatibility
    
    -   Verify version requirements
    -   Check dependency conflicts
2.  Verify Directory Permissions
    
        chmod -R 755 apps/
        chown -R www-data:www-data apps/
        
    
3.  Enable Plugin Debugging
    
        // In system/config.php
        define('PLUGIN_DEBUG', true);
        
    

## General Troubleshooting Tips

### Debug Mode Commands

    // Add to any page for detailed debugging
    _debug($variable);
    // Log to system log
    _log($message);
    

### Error Log Locations

-   Apache: `/var/log/apache2/error.log`
-   Nginx: `/var/log/nginx/error.log`
-   PHP: `/var/log/php_errors.log`
-   System: `storage/logs/system.log`

### Performance Optimization

1.  Enable PHP OPCache
    
        opcache.enable=1
        opcache.memory_consumption=128
        
    
2.  Implement Redis Cache
    
        define('CACHE_DRIVER', 'redis');
        define('REDIS_HOST', 'localhost');
        
    

### Security Checks

1.  File Permissions
    
        find . -type f -exec chmod 644 {} \;
        find . -type d -exec chmod 755 {} \;
        
    
2.  SSL Configuration
    
        SSLProtocol all -SSLv3 -TLSv1 -TLSv1.1
        SSLCipherSuite ECDHE-ECDSA-AES128-GCM-SHA256:ECDHE-RSA-AES128-GCM-SHA256
        
    

## When to Contact Support

Create a support ticket if:

-   Error persists after trying solutions
-   System security is compromised
-   Data integrity issues occur
-   Custom feature development needed

Include in your support ticket:

-   Error messages
-   Debug logs
-   Steps to reproduce
-   Recent system changes

Remember to always backup your data before attempting any troubleshooting steps that modify system files or database content.