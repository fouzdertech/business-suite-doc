# Managing Invoices

CloudOnex Business Suite provides comprehensive tools for creating, managing, and tracking invoices. This guide will help you effectively manage your invoicing process.

## Creating Invoices

### Basic Invoice Creation

1.  Navigate to **Sales** → **New Invoice**
2.  Fill in the required information:

    - Select customer from dropdown or add new customer
    - Choose invoice date
    - Set payment due date
    - Add invoice title (optional)
    - Add line items with quantities and prices
    - Select applicable tax rates
    - Add invoice terms

3.  Click actions:

    - **Save**: Save and continue editing
    - **Save & Close**: Save and view the invoice

### Invoice Numbering

- Default format: Set in Settings → General Settings
- Custom prefix options available
- Automatic sequential numbering
- Dynamic prefix support using placeholders:

      Example: INV-{date('Y-m-d')}-

### Adding Items to Invoice

1.  Click "Add Item" in the invoice
2.  Either:
    - Select from existing products/services
    - Add new item directly
3.  Specify:
    - Quantity
    - Price
    - Description
    - Tax rate (if applicable)

## Invoice Management

### Viewing Invoices

Access invoices through:

- **Sales** → **Invoices** for complete list
- Customer profile for customer-specific invoices
- Search functionality using invoice number

### Invoice Status Types

- **Draft**: Created but not sent
- **Sent**: Delivered to customer
- **Paid**: Full payment received
- **Partially Paid**: Some payment received
- **Overdue**: Payment past due date
- **Cancelled**: Cancelled invoice
- **Void**: Voided invoice

### Invoice Actions

From the invoice view, you can:

- Edit invoice details
- Send via email
- Print invoice
- Download PDF
- Record payments
- Clone invoice
- Delete invoice

## Payment Management

### Recording Payments

1.  Open the invoice
2.  Click "Add Payment"
3.  Enter payment details:
    - Amount
    - Date
    - Payment method
    - Transaction ID/reference
    - Notes

### Partial Payments

- System tracks remaining balance
- Multiple payments can be recorded
- Payment history maintained
- Automatic status updates
