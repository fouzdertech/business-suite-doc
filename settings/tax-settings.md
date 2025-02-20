# Tax Settings Configuration Guide

## Overview

FouzderIT Business Suite provides flexible tax configuration options to handle various tax systems and requirements across different jurisdictions. This guide explains how to configure and manage tax settings for your business needs.

## Basic Tax Configuration

### Setting Up Tax System

1.  Navigate to Settings → General Settings
2.  Locate "Tax System" dropdown
3.  Choose your tax system:
    -   Default (Standard tax rates)
    -   India GST
    -   Custom tax configuration

### Configuring Basic Tax Rates

1.  Go to Settings → Sales Tax
2.  Click "Add New Tax Rate"
3.  Configure:
    -   Tax Name (e.g., "VAT", "GST", "Sales Tax")
    -   Rate (percentage)
    -   Description
4.  Click "Save"

## EU VAT

-   You can add customer VAT info in the customer profile
-   You can set your VAT number in the Settings

## GST Configuration for India

### Enabling Indian GST

1.  Go to Settings → General Settings
2.  Set Tax System to "India"
3.  Select your default business location
4.  Save changes

### GST Components

Configure the following tax components:

-   CGST (Central GST)
-   SGST (State GST)
-   IGST (Integrated GST)
-   UTGST (Union Territory GST)

### GST Rate Configuration

1.  Navigate to Settings → Sales Tax
2.  Add GST rates for different categories:
    -   0% (Exempt)
    -   5%
    -   12%
    -   18%
    -   28%

### HSN/SAC Codes

1.  Go to Products & Services
2.  Edit each product/service
3.  Add relevant HSN/SAC code
4.  Save changes

## Tax Groups

### Creating Tax Groups

For multiple taxes applied to single items:

1.  Go to Settings → Sales Tax
2.  Click "New Tax Group"
3.  Configure:
    -   Group Name
    -   Select applicable taxes
    -   Set calculation method (compound or parallel)
4.  Save group

### Managing Tax Groups

1.  Select tax groups when:
    -   Creating products
    -   Adding invoice items
    -   Generating quotes
2.  System automatically calculates combined taxes

## Tax Categories

### Product-Specific Tax Rates

1.  Go to Settings → Sales Tax
2.  Create tax categories
3.  Assign to products/services
4.  System applies appropriate rates on invoices

### Service-Specific Tax Rates

1.  Create separate tax categories for services
2.  Assign to service items
3.  Configure different rates if required

## Regional Tax Settings

### Multi-State Tax Configuration

For businesses operating in multiple states:

1.  Configure state-wise tax rates
2.  Set default state
3.  Enable location-based tax calculation
4.  Configure tax jurisdictions

### International Tax Settings

For international businesses:

1.  Configure country-specific tax rates
2.  Set up tax rules for exports
3.  Configure import duties if applicable
4.  Enable currency-specific tax calculations