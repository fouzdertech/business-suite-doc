# Users and Roles Management

## Overview

One of the important features of the admin area is controlling what admins can access and manage. For example, you may want to give a salesperson different access than support operators. FouzderIT Business Suite allows you to manage users and their access permissions through a robust user and role management system. You can add unlimited users and assign specific roles to control what features and data they can access within the system.

## Managing Users

### Adding New Users

1.  Navigate to Settings → Users
2.  Click on the "Add New User" button
3.  Fill out the user form with the following information:
    -   Full Name
    -   Email Address (will be used as username)
    -   Password
    -   User Type (Admin or Employee)
    -   Assign Role (select from pre-configured roles)
4.  Click "Save" to create the user

### Managing Existing Users

-   View all users from Settings → Users
-   Edit user details by clicking the edit icon
-   Deactivate/reactivate users as needed
-   Reset user passwords
-   Change user roles

## Role Management

### Understanding Roles

Roles are collections of permissions that define what actions a user can perform within the system. This allows for granular control over system access.

### Creating New Roles

1.  Go to Settings → Roles
2.  Click "New Role" button
3.  Enter role name
4.  Set permissions by checking/unchecking boxes for different modules:
    -   View: Allows viewing data
    -   Edit: Allows modifying existing data
    -   Create: Allows creating new data
    -   Delete: Allows deleting data
    -   All Data: Access to data created by all users (if unchecked, users can only access their own data)

### Permission Modules

Roles can be configured with different permission levels for various modules including:

-   Sales
-   Purchases
-   Customers
-   Banking & Transactions
-   Reports
-   Products & Services
-   Support Tickets
-   And more

### Example Role Configurations

#### Sales Representative Role

    - Customers: View, Create, Edit
    - Sales: View, Create
    - Products: View
    - Reports: View (own data only)
    

#### Support Staff Role

    - Support Tickets: View, Create, Edit
    - Customers: View
    - Knowledge Base: View, Create, Edit