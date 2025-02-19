# PDF Generation Troubleshooting Guide

## Common PDF Generation Issues

### 1\. Blank PDF Files

If you're getting blank PDF files when generating invoices or other documents:

-   Ensure your PHP memory\_limit is set to at least 128M in your php.ini file
-   Verify that the GD PHP extension is enabled on your server
-   Check if you have write permissions in the temp directory
-   Make sure all required fonts are properly installed

### 2\. Missing Images or Logos

If images or your company logo aren't appearing in generated PDFs:

-   Confirm that your logo file exists in the correct directory
-   Verify the image file permissions (should be readable)
-   Try re-uploading your logo through Appearance → Customize
-   Use supported image formats (PNG, JPG, GIF)
-   Check if the image path in your custom template is correct

### 3\. Character Encoding Issues

If you see question marks or incorrect characters in your PDFs:

-   Ensure you're using UTF-8 encoding in your system settings
-   If using a custom template, verify the encoding of your template file
-   Check if you're using a compatible font that supports your language characters
-   Try changing the PDF font in Settings → General Settings

Set a different font, and try loading pdf file again-

<img title="" src="./sms_img/2024-12-02-at-100315-at-2x.webp" alt="asd" data-align="center" width="490">

### 4\. Layout Problems

If the PDF layout appears broken or misaligned:

-   Clear your browser cache and try regenerating the PDF
-   If using a custom template, verify your HTML structure
-   Check if all CSS styles are properly defined
-   Ensure your template is compatible with the current version of Business Suite