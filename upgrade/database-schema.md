# Manual Database Schema Update

During business suite updates, the system generally redirects to the page where it updates the required database schema. However, in some cases, if it fails, you can revisit the page later, and it will re-run the script to make the necessary database schema updates.

If the automatic schema update fails:

-   Visit: `your-domain/?ng=updating/schema`
-   Or with URL rewrite enabled: `your-domain/updating/schema`

For example, we might add a new database column to add a feature. Updating database schema makes sure you have the latest database changes.