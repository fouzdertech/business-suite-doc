# Editing Layouts

CloudOnex Business Suite allows you to customize the layout and structure of both admin and client portals by modifying template files. This guide explains how to safely and effectively edit system layouts to match your business needs.

## Understanding Layout Structure

### Template Locations

1.  **Admin Portal Layout**
    
        /ui/theme/default/layouts/admin.tpl
        
    
2.  **Client Portal Layout**
    
        /ui/theme/default/layouts/client.tpl
        
    

### Layout Components

-   Navigation menus
-   Header sections
-   Sidebar elements
-   Footer content
-   Content areas
-   Widget placement

## Basic Layout Customization

### Editing Navigation Menus

1.  **Access Template Files**
    
        1. Navigate to /ui/theme/default/layouts/
        2. Open admin.tpl or client.tpl using a text editor
        3. Locate the navigation section
        
    
2.  **Menu Structure Example**
    
        <ul class="nav">
            <li class="nav-item">
                <a href="{$_url}dashboard" class="nav-link">
                    <i class="nav-icon fas fa-tachometer-alt"></i>
                    <p>Dashboard</p>
                </a>
            </li>
        </ul>
        
    

### Modifying Header Elements

1.  **Header Customization**
    
        <header class="main-header">
            <!-- Company Logo -->
            <a href="{$_url}dashboard" class="logo">
                <span class="logo-lg">
                    <img src="{$app_url}storage/system/{$config['logo_default']}" alt="Logo">
                </span>
            </a>
            <!-- Other Header Elements -->
        </header>