# Receiving Payments

CloudOnex Business Suite provides multiple ways to receive and record payments from customers. This guide covers all aspects of payment processing and management.

## Recording Payments

### Manual Payment Recording

1.  Navigate to the invoice:

    - Go to **Sales** → **Invoices**
    - Click on the specific invoice
    - Click "Add Payment"

2.  Enter payment details:

        Required fields:
        - Payment amount
        - Payment date
        - Payment method

        Optional fields:
        - Transaction ID
        - Notes
        - Attachments (e.g., payment receipt)

3.  Click "Submit" to record the payment

## Payment Methods

### Available Payment Methods

CloudOnex supports various payment methods:

1.  **Online Payments**

    - PayPal
    - Stripe
    - Other payment gateways via plugins

2.  **Traditional Methods**

    - Bank transfer
    - Check
    - Cash
    - Wire transfer

### Configuring Payment Methods

1.  Navigate to **Settings** → **Payment Gateways**
2.  Available options:
    - Enable/disable methods
    - Configure gateway credentials
    - Set processing fees
    - Customize payment instructions

## Online Payment Processing

### PayPal Integration

1.  Configure PayPal:

    - Enter PayPal email
    - Set API credentials
    - Configure IPN URL
    - Test connection

2.  Customer experience:

    - Click "Pay Now"
    - Redirect to PayPal
    - Complete payment
    - Automatic invoice update

### Stripe Integration

1.  Setup requirements:

    - API keys
    - Webhook configuration
    - Currency settings
    - Payment methods

2.  Features:

    - Card payments
    - Direct charges
    - Subscription handling
    - Refund processing

## Payment Tracking

### Payment Status

Monitor payments through:

1.  **Dashboard Overview**

    - Recent payments
    - Pending payments
    - Failed transactions
    - Payment trends

2.  **Detailed Reports**

    - Payment history
    - Transaction details
    - Payment methods used
    - Success rates

### Transaction Records

Each payment record includes:

- Payment amount
- Payment date
- Method used
- Transaction ID
- Associated invoice
- Processing fees
- Notes and attachments

## Customer Portal Payments

### Enable Online Payments

1.  Configure portal settings:

    - Enable payment features
    - Select payment methods
    - Set payment terms
    - Configure notifications

2.  Customer features:

    - View invoices
    - Make payments
    - View payment history
    - Download receipts

## Automated Processes

### Payment Reminders

Setup automatic reminders:

1.  Configure in **Settings** → **Automation Settings**
2.  Set reminder schedule:
    - Before due date
    - On due date
    - After due date
    - Custom intervals

### Receipt Generation

Automatic receipt features:

- Generate after payment
- Email to customer
- Store in system
- Attach to transaction record
