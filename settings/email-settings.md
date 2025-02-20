# Email Configuration Guide

## Overview

Email configuration is a crucial part of FouzderIT Business Suite, enabling the system to send invoices, notifications, password resets, and other important communications. This guide covers all aspects of email configuration and troubleshooting.

## Email Drivers

FouzderIT Business Suite supports multiple email sending methods to accommodate different hosting environments and requirements.

### 1\. PHP Mail

The simplest configuration using the PHP `mail()` function.

#### Configuration Steps:

1. Select "PHP Mail" from the "Send Email Using" dropdown
2. Enter your system email address
3. Enter your sender name
4. Save settings

> **Note:** PHP Mail is not recommended for production use as emails may be marked as spam. Use SMTP instead for better deliverability.

### 2\. SMTP Configuration

SMTP is the recommended method for sending emails reliably.

#### Required Information:

- SMTP Host (e.g., smtp.gmail.com, smtp.office365.com)
- SMTP Username
- SMTP Password
- SMTP Port (common ports: 25, 465, 587)
- Security Protocol (SSL/TLS)

#### Configuration Steps:

1. Select "SMTP" from the "Send Email Using" dropdown
2. Enter your System Email Address
3. Enter your Default Sender Name
4. Fill in the SMTP details:
   - Host address
   - Username
   - Password
   - Port number
   - Select security protocol (SSL/TLS)
5. Click Save

### 3\. Mailgun Integration

For high-volume email sending, Mailgun offers reliable delivery.

#### Prerequisites:

- Active Mailgun account
- Domain verified with Mailgun
- API key from Mailgun

#### Configuration Steps:

1. Select "Mailgun" from the "Send Email Using" dropdown
2. Enter your Mailgun domain
3. Enter your Mailgun API key
4. Save settings

## Testing Email Configuration

After setting up your email configuration:

1. Go to Email Settings
2. Enter a test email address
3. Click "Send Test Email"
4. Check the recipient inbox
5. Verify email logs in System → Email Log

## Troubleshooting

### Common Issues and Solutions

#### 1\. Connection Timeout

    SMTP ERROR: Failed to connect to server: Connection timed out (110)

**Solutions:**

- Check if SMTP port is blocked by firewall
- Verify correct port number
- Ensure server can reach SMTP host

#### 2\. Authentication Failed

    SMTP ERROR: Authentication failed

**Solutions:**

- Double-check username and password
- For Gmail: Enable "Less secure app access" or use App Password
- Verify correct SMTP security protocol

#### 3\. Debug Mode for Detailed Errors

To enable detailed error reporting:

1. Edit `system/config.php`
2. Change APP\_STAGE from 'Live' to 'Dev'
3. Retry the email operation
4. Check error messages in the browser

## Email Templates

FouzderIT Business Suite includes customizable email templates for:

- Invoice notifications
- Quote notifications
- Payment receipts
- Password resets
- System notifications

### Available Template Variables

| Variable             | Description          |
|----------------------|----------------------|
| {name}              | Customer name        |
| {business_name}     | Your company name    |
| {invoice_url}       | Invoice preview URL  |
| {invoice_id}        | Invoice ID           |
| {invoice_status}    | Invoice status       |
| {invoice_amount_paid} | Amount paid        |
| {invoice_due_amount}  | Amount due         |
| {invoice_date}      | Invoice date         |




