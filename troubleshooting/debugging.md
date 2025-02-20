# Debug Mode

Debug Mode is a powerful troubleshooting tool in FouzderIT Business Suite that helps identify and resolve issues by providing detailed error information. This guide explains how to use Debug Mode effectively and safely.

## Enabling Debug Mode

### Basic Configuration

1.  **Access Config File**
    
    -   Open `system/config.php` using any text editor
    -   Locate the following line:
    
        define('APP_STAGE', 'Live');
        
    
    -   Change it to:
    
        define('APP_STAGE', 'Dev');
        
    

### Important Security Note

> ⚠️ **Warning**: Only enable Debug Mode temporarily for troubleshooting. Always disable it in production environments to prevent exposing sensitive information.

## What Debug Mode Does

1.  **Enhanced Error Reporting**
    
    -   Displays detailed error messages
    -   Shows exact file locations and line numbers
    -   Provides code snippets around error locations
    -   Records comprehensive system logs
2.  **Email System Logging**
    
    -   Tracks detailed email sending attempts
    -   Records SMTP communication logs
    -   Stores email rendering information

## Debugging JavaScript Issues

### Using Browser Developer Tools

1.  **Open Developer Console**
    
    -   Right-click on any empty space on the page
    -   Select "Inspect" or press:
        -   Windows/Linux: `Control+Shift+I`
        -   Mac: `Command+Option+I`
    -   Click on the "Console" tab
2.  **Reading Error Messages**
    
    -   Red text indicates errors
    -   Yellow warnings show potential issues
    -   Stack traces show error origins

## Debugging AJAX Requests

1.  **Network Tab Analysis**
    
    -   Open Developer Tools
    -   Select the "Network" tab
    -   Click "Fetch/XHR" sub-tab
    -   Perform the action that's failing
    -   Click on the relevant request URL
2.  **Common AJAX Issues**
    
    -   Look for:
        -   HTTP status codes
        -   Response data
        -   Request headers
        -   Error messages in response

## Troubleshooting Steps

1.  **Initial Investigation**
    
    -   Enable Debug Mode
    -   Clear browser cache
    -   Reproduce the issue
    -   Document the error messages
2.  **Log Analysis**
    
    -   Check system logs
    -   Review error messages
    -   Note any patterns or recurring issues
3.  **Common Issues and Solutions**
    
    a. **Blank Page**
    
    -   Enable Debug Mode
    -   Check PHP error logs
    -   Verify PHP memory limits
    -   Review database connections
    
    b. **Database Errors**
    
    -   Confirm database credentials
    -   Check database permissions
    
    c. **JavaScript Errors**
    
    -   Check browser console
    -   Verify script loading order
    -   Look for syntax errors

**Error Documentation** - Screenshot error messages - Note steps to reproduce issues

## Getting Help

If you cannot resolve an issue using Debug Mode:

1.  **Support Resources**
    
    -   Check FouzderIT documentation
2.  **Contacting Support**
    
    -   Provide Debug Mode screenshot
    -   Share steps to reproduce
    -   Include system environment details
    -   Describe expected vs actual behavior

## Disabling Debug Mode

After completing troubleshooting:

1.  **Restore Production Settings**
    
    -   Edit `system/config.php`
    -   Change back to:
    
        define('APP_STAGE', 'Live');