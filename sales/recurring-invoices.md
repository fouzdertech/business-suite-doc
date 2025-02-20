# Recurring Invoices

Recurring invoices in FouzderIT Business Suite allow you to automatically generate and send invoices at specified intervals. This feature is ideal for subscription-based services, retainers, or any regular billing needs.

## Understanding Recurring Invoices

### Overview

Recurring invoices automatically:

- Generate new invoices at set intervals
- Maintain consistent invoice numbering
- Send to customers automatically
- Track payment status
- Manage subscription billing

## Creating Recurring Invoices

### Basic Setup

1.  Navigate to **Sales** → **New Recurring Invoice**
2.  Fill in the standard invoice details:
    - Select customer
    - Add products/services
    - Set amounts
    - Add terms if needed

### Recurring Settings

Configure recurrence options:

1.  **Repeat Every**: Choose frequency

    - Daily
    - Weekly
    - Bi-weekly (2 Weeks)
    - Monthly
    - Quarterly (3 months)
    - Semi-annually (6 months)
    - Annually
    - Biennially (2 Years)
    - Triennially (3 Years)

2.  **Start Date**: First invoice generation date
3.  **End Settings** (Optional):

    - Never (continuous)
    - After specific number of invoices
    - Until specific date

## Automation Setup

### Configuring CRON Jobs

1.  Go to **Settings** → **Automation Settings**
2.  Set up CRON job using the provided command:

        * * * * * php /path/to/system/cron.php

### Email Notifications

Configure automatic emails for:

- New invoice generation
- Payment reminders
- Payment receipts
- Late payment notices

## Managing Recurring Invoices

### Viewing Recurring Invoices

1.  Navigate to **Sales** → **Recurring Invoices**
2.  View list showing:
    - Customer name
    - Amount
    - Frequency
    - Next due date
    - Status
