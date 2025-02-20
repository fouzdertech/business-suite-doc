# Localization Settings Guide

## Overview

FouzderIT Business Suite can be configured for different languages, date formats, time zones, and regional preferences. This guide covers all localization settings to help you adapt the system to your local requirements.

## Language Configuration

### Available Languages

FouzderIT supports numerous languages including:

| Language      | ISO Code | Region         |
| ------------- | -------- | -------------- |
| English (USA) | en       | United States  |
| English (UK)  | en_gb    | United Kingdom |
| English (AU)  | en_au    | Australia      |
| español       | es       | Spanish        |
| français      | fr       | French         |
| Deutsch       | de       | German         |
| italiano      | it       | Italian        |
| português     | pt       | Portuguese     |
| русский       | ru       | Russian        |
| 日本語        | ja       | Japanese       |
| 中文          | zh       | Chinese        |
| العربية       | ar       | Arabic         |


### Setting System Language

1.  Navigate to Settings → Localization Settings
2.  Select default system language
3.  Click Save Changes

### User-Specific Language

Users can set their preferred language:

1.  Click profile menu in top right
2.  Select "Edit Profile"
3.  Choose preferred language
4.  Save changes

## Date and Time Settings

### Time Zone Configuration

1.  Go to Settings → Localization Settings
2.  Select your time zone from the dropdown
3.  Save changes

### Date Format Settings

Available date formats:

-   YYYY-MM-DD (2024-01-31)
-   DD-MM-YYYY (31-01-2024)
-   MM-DD-YYYY (01-31-2024)
-   DD.MM.YYYY (31.01.2024)
-   DD/MM/YYYY (31/01/2024)

To configure:

1.  Choose preferred format from dropdown
2.  Set date separator (- / .)
3.  Save changes

### Time Format

Choose between:

-   24-hour format (14:30)
-   12-hour format (2:30 PM)

## Number Formatting

### Decimal Settings

Configure:

1.  Decimal separator (. or ,)
2.  Thousand separator (, or .)
3.  Number of decimal places
4.  Digit grouping style

Example configurations:

-   US Style: 1,234.56
-   European Style: 1.234,56

### Currency Display

Set currency display preferences:

1.  Symbol position (before/after amount)
2.  Space between symbol and amount
3.  Decimal places for currency
4.  Currency symbol display style

## Regional Settings

### Business Location

1.  Set primary business location
2.  Configure regional business number format
3.  Set local tax system
4.  Enable relevant regional features

### Address Format

Configure address display order:

1.  Street address
2.  City/Town
3.  State/Province
4.  Postal/ZIP code
5.  Country

Example formats:

    US Format:
    Street Address
    City, State ZIP
    Country
    
    UK Format:
    Street Address
    City/Town
    County
    Postal Code
    Country
    

## Customizing Language Files

### Editing Translations

1.  Locate language files in `system/i18n/`
2.  Create override file:
    -   Rename `system/overrides/i18n.sample.php` to `i18n.php`
    -   Add custom translations

Example override:

    return [
        'invoice' => 'Custom Invoice Text',
        'payment' => 'Custom Payment Text'
    ];
    

### Adding New Languages

1.  Copy `en.php` from `system/i18n/`
2.  Rename to new language code
3.  Translate contents
4.  Add language to system settings

## Calendar Settings

### Week Configuration

Set:

-   First day of week
-   Working days
-   Weekend days
-   Holiday calendar

### Business Hours

Configure:

1.  Business day start time
2.  Business day end time
3.  Break times
4.  Time slots

## Document Templates

### Localized Templates

Customize for each language:

1.  Invoice templates
2.  Quote templates
3.  Email templates
4.  PDF documents

### Variable Placeholders

Use localized variables:

    {DATE_FORMATTED}
    {CURRENCY_SYMBOL}
    {CUSTOMER_ADDRESS}