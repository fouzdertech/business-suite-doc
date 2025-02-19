# Troubleshooting

### If You Encounter Issues

1.  **Enable Developer Mode**
    
    -   Open `system/config.php`
    -   Change `APP_STAGE` from `'Live'` to `'Dev'`
    
        define('APP_STAGE', 'Dev');
        
    
    -   This will display detailed error messages
2.  **Manual Database Schema Update** If the automatic schema update fails:
    
    -   Visit: `your-domain/?ng=updating/schema`
    -   Or with URL rewrite enabled: `your-domain/updating/schema`

### Common Issues and Solutions

1.  **Blank Screen After Update**
    
    -   Enable Dev mode as described above
    -   Check PHP error logs
    -   Verify PHP version compatibility
2.  **Database Errors**
    
    -   Ensure your MySQL version meets requirements
    -   Try manual schema update
    -   Restore from backup if necessary
3.  **Custom Modifications**
    
    -   If you've customized your installation, you'll need to reapply modifications
    -   Keep a log of all customizations for future updates