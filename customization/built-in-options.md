# Built-in Customization Options

FouzderIT Business Suite offers extensive customization options to tailor the system to your business needs. This guide covers the built-in customization features available through the administrative interface.

## Visual Customization

### Company Branding

1.  **Logo Customization**
    -   Navigate to `Appearance → Customize`
    -   Upload your company logo
    -   Click "Submit" to save changes
    -   Note: If you see the old logo, clear your browser cache

### Theme Settings

1.  **Theme Selection**
    -   Go to `Appearance → Themes`
    -   Choose your preferred theme
    -   Select the desired style variation
    -   Changes apply immediately across the system

### Invoice Customization

1.  **Enable Signature Feature**
    
    -   Navigate to `Appearance → Customize`
    -   Check the "Enable signature" checkbox
    -   Save changes
2.  **Dynamic Invoice Prefix**
    
    -   Go to `Settings → General Settings`
    -   In the invoice prefix field, use placeholders
    -   Example: `INV-{date('Y-m-d')}-`
    -   You can modify the date format within the date function

## Language and Localization

### Time Zone and Date Format

1.  **Time Zone Settings**
    -   Navigate to `Settings → Localization`
    -   Select your preferred timezone
    -   Choose your desired date format
    -   Save changes

### Language Settings

1.  **System Language**
    
    -   Go to `Settings → Localization Settings`
    -   Select your default system language
2.  **Per-User Language**
    
    -   Users can set their preferred language
    -   Navigate to `Edit Profile` in the top right corner
    -   Select desired language
    -   Changes apply only to that user's interface

## Business Information

### Company Details

1.  **Basic Information**
    -   Navigate to `Settings → General Settings`
    -   Update company name, address, and contact details
    -   Modify business registration numbers (VAT/ABN)
    -   Set default payment terms

### Tax Configuration

1.  **GST Configuration (India)**
    -   Go to `Settings → General Settings`
    -   Set Tax System to "India"
    -   Select your default business location
    -   System will automatically format invoices for GST compliance

## Customer-Related Customization

### Custom Fields

1.  **Adding Custom Contact Fields**
    -   Navigate to `Settings → Custom Contact Fields`
    -   Add new fields as needed
    -   Fields appear on customer forms

### Customer Code Format

1.  **Configure Customer Numbering**
    -   Go to `Settings → General Settings`
    -   Set customer code prefix
    -   Configure auto-increment settings
    -   Example: `CUS-000001` will automatically increment to `CUS-000002`

## Landing Page Configuration

### Default Page Selection

1.  **Set Default Landing Page**
    -   Navigate to `Settings → General Settings`
    -   Choose between admin login or client login as default
    -   Alternative access URLs:
        -   Admin login: `your_installation_url/admin`
        -   Client login: `your_installation_url/client`

## Advanced Customization

### PDF Invoice Template

1.  **Custom Template**
    -   Locate `system/overrides/invoice_pdf.sample.php`
    -   Rename to `invoice_pdf.php`
    -   Modify the template as needed
    -   Changes persist through system updates

### Additional Display Options

1.  **Contact Display Name**
    -   Go to `Settings → General Settings`
    -   Modify the "Extra Field Name" setting
    -   Changes apply to all contact forms