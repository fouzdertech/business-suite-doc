# SMS Configuration Guide

## Overview

FouzderIT Business Suite provides SMS functionality for sending notifications, alerts, and communications to customers. This guide covers SMS configuration, available drivers, and troubleshooting steps.

## SMS Drivers Configuration

### Nexmo (Vonage)

#### Prerequisites

-   Active Nexmo/Vonage account
-   API Key and Secret from Nexmo Dashboard

#### Configuration Steps

1.  Navigate to SMS → Settings
2.  Select "Nexmo" from the driver list
3.  Configure the following:
    -   **Sender ID**: Your company name (max 11 characters) or phone number
    -   **API Key**: Your Nexmo API key
    -   **API Secret**: Your Nexmo API secret
4.  Click "Save"

### Twilio

#### Prerequisites

-   Twilio account
-   Account SID and Auth Token
-   Verified Twilio phone number

#### Configuration Steps

1.  Go to SMS → Settings
2.  Select "Twilio" from the driver list
3.  Enter:
    -   **SID**: Your Twilio Account SID
    -   **Token**: Your Twilio Auth Token
    -   **From Number**: Your Twilio phone number
4.  Save configuration

### Route SMS / Route Mobile

#### Prerequisites

-   Route SMS account
-   API credentials

#### Configuration Steps

1.  Access SMS → Settings
2.  Choose "Routesms" as the driver
3.  Enter the following details:
    -   **HTTP API URL**: Your Route SMS API endpoint
    -   **Username**: Route SMS username
    -   **Password**: Route SMS password
4.  Save settings

### Infobip

#### Prerequisites

-   Infobip account
-   API credentials and endpoint

#### Configuration Steps

1.  Navigate to SMS → Settings
2.  Select "Infobip" from drivers
3.  Configure:
    -   **HTTP API URL**: Your Infobip endpoint (e.g., [https://xyz.api.infobip.com](https://xyz.api.infobip.com/))
    -   **Username**: Infobip username
    -   **Password**: Infobip password
4.  Save configuration

## Custom SMS Gateway Integration

### Configuration Format

1.  Select "Custom" as SMS driver
2.  Configure the HTTP endpoint:
    
        API URL: https://gateway.example.com/send
        
    
3.  Set parameters using placeholders:
    
        to={{to}},from={{from}},message={{message}},username=YourUsername,password=YourPassword
        
    

### Parameter Guidelines

-   Use double equals (==) for parameter assignment
-   Separate parameters with commas
-   Available placeholders:
    -   {{to}} - Recipient number
    -   {{from}} - Sender ID
    -   {{message}} - SMS content

## Testing SMS Configuration

### Test Message Steps

1.  Go to SMS → Settings
2.  Enter a test phone number
3.  Click "Send Test SMS"
4.  Check delivery status
5.  Verify SMS logs

### Troubleshooting Test Messages

If test message fails:

1.  Verify API credentials
2.  Check phone number format
3.  Review error logs
4.  Confirm account balance
5.  Test API endpoint accessibility

## SMS Features

### Bulk SMS

Send messages to multiple recipients:

1.  Go to SMS → Bulk SMS
2.  Upload recipient list or select contacts
3.  Compose message
4.  Schedule or send immediately
5.  Monitor delivery status

### SMS Templates

Create reusable message templates:

1.  Navigate to SMS → Templates
2.  Click "Add New Template"
3.  Enter template name
4.  Compose message with variables
5.  Save template