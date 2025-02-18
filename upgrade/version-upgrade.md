# CloudOnex Business Suite - Version Upgrade Guide

## Before You Begin

### Prerequisites

-   PHP 8.3 or higher
-   MySQL 5.7 or higher
-   Required PHP Extensions:
    -   Mbstring
    -   PDO
    -   GD
    -   JSON

### Important Safety Measures

⚠️ **CRITICAL:** Always create a complete backup before starting any upgrade process.

-   Back up all application files
-   Export a complete database backup
-   Document any custom modifications you've made to the system

## Upgrade Methods

### Method 1: Using the Updater Plugin (Recommended)

This is the simplest and safest method for most users.

1.  **Download the Updater Plugin**
    
    -   Get the free updater plugin from [CloudOnex website](https://fromcdn.sfo3.digitaloceanspaces.com/sp/cloudonex/media/updater.zip)
2.  **Install the Plugin**
    
    -   Upload and install the updater plugin through your Business Suite dashboard
    -   A new "Updater" menu will appear under Settings
3.  **Perform the Update**
    
    -   Navigate to Settings → Updater
    -   Follow the on-screen instructions to complete the update
    -   The plugin will automatically handle database backups and file updates

### Method 2: Manual Update

For developers or users who need more control over the update process.

1.  **Prepare for Update**
    
    -   Download the latest version from your CloudOnex dashboard
    -   Create a complete backup of your current installation
    -   Export your database
2.  **Update Files**
    
    -   Upload the new version's ZIP file to your server
    -   Extract the files directly on the server
    -   For cPanel users: Use File Manager to extract
    -   For VPS users: Use the unzip command in terminal
3.  **Database Update**
    
    -   Log in to your Business Suite
    -   You will be automatically redirected to the update page
    -   The system will update the database schema if needed
4.  **Verify Configuration**
    
    -   Your existing config file (`system/config.php`) will be preserved
    -   No need to reconfigure database settings