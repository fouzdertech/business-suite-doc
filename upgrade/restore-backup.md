## Restoring Files and Database

To restore the business suite from a backup, follow these steps:

1.  Upload the zip file to your hosting account.
2.  Create a new database in your hosting environment and import the database from the backup.
3.  Update the system/config.php file with the new database credentials and the updated URL information.
4.  Finally, visit the URL to access the business suite application.

## Restoring Database Only

If you want to restore only the database, first back up your current database. Then, drop all tables and import the backup database using phpMyAdmin or another database administration tool.