# Payment Gateways Configuration Guide

## Overview

CloudOnex Business Suite supports multiple payment gateways to process customer payments. This guide covers the configuration of built-in payment gateways and available payment gateway plugins.

## Built-in Payment Gateways

### PayPal Configuration

#### Prerequisites

-   PayPal Business Account
-   API credentials from PayPal Developer Dashboard

#### Configuration Steps

1.  Navigate to Settings → Payment Gateways
2.  Locate PayPal in the list
3.  Click "Configure"
4.  Enter the following details:
    -   PayPal Email Address
    -   API Username
    -   API Password
    -   API Signature
5.  Set "Enable Gateway" to "Yes"
6.  Click "Save Changes"

### Stripe Configuration

#### Prerequisites

-   Stripe Account
-   API Keys from Stripe Dashboard

#### Configuration Steps

1.  Navigate to Settings → Payment Gateways
2.  Find Stripe in the gateway list
3.  Click "Configure"
4.  Enter the following credentials:
    -   Publishable Key
    -   Secret Key
5.  Set "Enable Gateway" to "Yes"
6.  Click "Save Changes"

### Bank Transfer Configuration

For manual bank transfer payments:

1.  Go to Settings → Payment Gateways
2.  Locate Bank Transfer
3.  Click "Configure"
4.  Enter your bank details:
    -   Bank Name
    -   Account Name
    -   Account Number
    -   Branch
    -   IFSC/SWIFT Code
5.  Add payment instructions
6.  Enable the gateway
7.  Save changes

## Available Payment Gateway Plugins

CloudOnex Business Suite offers additional payment gateway integrations through plugins:

### Regional Payment Gateways

-   PayUMoney (India)
-   CCAvenue (India)
-   Razorpay (India)
-   Paytm (India)
-   Payhere (Sri Lanka)
-   WidePay (Brazil)
-   Mercadopago (Latin America)

### International Payment Gateways

-   Adyen
-   Vivawallet
-   Bluesnap
-   Square (USA)
-   Mollie
-   Paystack
-   Foloosi

## Installing Payment Gateway Plugins

1.  Purchase the desired plugin from CloudOnex Marketplace
2.  Download the plugin ZIP file
3.  Go to Plugins in your Business Suite
4.  Click "Upload Plugin"
5.  Select the downloaded ZIP file
6.  Click "Install"
7.  Configure the gateway settings

## General Configuration Tips

### Testing Mode

Before going live:

1.  Enable test/sandbox mode
2.  Perform test transactions
3.  Verify payment notifications
4.  Check transaction logs
5.  Test refund process

### Security Best Practices

-   Keep API credentials secure
-   Use HTTPS for payment pages
-   Regularly update plugin versions
-   Monitor transaction logs
-   Implement fraud prevention measures

## Payment Flow

### Standard Payment Process

1.  Customer selects payment method
2.  System redirects to payment gateway
3.  Customer completes payment
4.  Gateway sends confirmation
5.  System updates invoice status
6.  Customer receives receipt

### Multiple Gateway Setup

When multiple gateways are enabled:

-   Customers see payment options at checkout
-   Each gateway shows its payment button
-   System tracks payment method used
-   Reports show gateway-wise transactions

## Troubleshooting

### Common Issues

#### Gateway Not Showing

-   Check if gateway is enabled
-   Verify API credentials
-   Check SSL certificate
-   Review error logs

#### Payment Failed

1.  Check gateway error message
2.  Verify transaction in gateway dashboard
3.  Confirm correct currency configuration
4.  Check payment amount matches invoice

#### Integration Issues

1.  Enable debug mode
2.  Check system logs
3.  Verify webhook URLs
4.  Confirm IPN/notification settings

## Transaction Management

### Viewing Transactions

1.  Go to Sales → Payments
2.  Filter by payment gateway
3.  View transaction details
4.  Check payment status
5.  Access gateway reference

## Currency Configuration

For multi-currency support:

1.  Configure base currency
2.  Set up currency conversion rates
3.  Enable currencies in gateway settings
4.  Test payments in different currencies

## Additional Resources

### Documentation Links

-   [PayPal Integration Guide](https://developer.paypal.com/docs/)
-   [Stripe Documentation](https://stripe.com/docs)
-   [CloudOnex Plugin Marketplace](https://www.cloudonex.com/marketplace)