# General Settings Configuration Guide

The General Settings page in FouzderIT Business Suite allows you to configure core system settings and customize the application according to your business needs. This guide covers all available options and their purposes.

## Basic Settings

### Company Information

-   **Application Name/Company Name**: Enter your business name that will appear on your logo, emails, and documents
-   **Default Landing Page**: Choose between Admin Login or Client Portal as your default landing page
-   **Pay To Address**: Enter your company's payment address that will appear on invoices and other documents
-   **Address Format**: Select your preferred address format based on your country/region
-   **Business Location**: Specify your primary business location
-   **Tax System**: Choose your tax system (Default, India GST, or others based on your region)

### Business Identifiers

-   **TAX/VAT Number**: Enter your business tax identification number
-   **Tax/VAT Number Label**: Customize the label that appears for tax numbers (e.g., VAT, GST, ABN)

## Document Settings

### Invoice Configuration

-   **Default Invoice Terms**: Set standard terms that will appear on all invoices
-   **PDF Font**: Select the font family for PDF documents
-   **Payment Terms**: Configure default payment terms for invoices

### Numbering Prefixes and Sequences

-   **Customer Code Prefix**: Set prefix for customer identification (e.g., CUS-)
-   **Invoice Prefix**: Configure prefix for invoice numbers (e.g., INV-)
-   **Purchase Order Prefix**: Set prefix for purchase orders (e.g., PO-)
-   **Quote Prefix**: Configure prefix for quotations (e.g., QUOTE-)
-   **Income Code Prefix**: Set prefix for income transactions (e.g., INC-)
-   **Expense Code Prefix**: Configure prefix for expense transactions (e.g., EXP-)
-   **Ticket Prefix**: Set prefix for support tickets

### Number Sequences

-   **Customer Code Number**: Set starting number for customer codes
-   **Invoice Number**: Configure starting number for invoices
-   **Purchase Order Number**: Set starting number for purchase orders
-   **Quote Number**: Configure starting number for quotes
-   **Income Code Number**: Set starting number for income transactions
-   **Expense Code Number**: Configure starting number for expenses
-   **Ticket Number**: Set starting number for support tickets

## Security Settings

### Google reCAPTCHA (v3)

-   **Enable reCAPTCHA**: Toggle reCAPTCHA protection
-   **reCAPTCHA Site Key**: Enter your Google reCAPTCHA site key
-   **reCAPTCHA Secret Key**: Enter your Google reCAPTCHA secret key

## Integration Settings

### API and External Services

-   **Google Maps API Key**: Enter your Google Maps API key for location services
-   **Slack Webhook URL**: Configure Slack integration for notifications

## Additional Settings

### Contact Fields

-   **Contact Extra Field Name**: Add custom fields for contact information
-   **Display Name**: Configure how contact names are displayed in the system

### System Options

-   **URL Rewrite**: Enable/disable URL rewriting for cleaner URLs
-   **Default Quantity**: Set default quantity value for new items

## Saving Changes

After making any changes to the General Settings:

1.  Review all modified settings
2.  Click the "Submit" button at the bottom of the page
3.  Wait for the confirmation message indicating settings have been saved

## Important Notes

-   Some settings (like URL rewriting) may require server configuration
-   Changes to numbering sequences will only affect new documents/records
-   It's recommended to configure essential settings like company information and tax settings immediately after installation
-   Take special care when modifying number sequences as they affect your business documentation
-   Keep security credentials (API keys, webhook URLs) secure and regularly updated