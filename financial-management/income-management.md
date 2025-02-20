# Income Management in FouzderIT Business Suite

### Overview

FouzderIT Business Suite provides robust tools for tracking and managing your business income. This guide will help you understand how to record, categorize, and monitor your income effectively.

## Recording Income

#### Adding a New Income Entry

1. Navigate to **Accounting → New Deposit**
2. Fill in the required fields:
   - **Amount**: Enter the income amount
   - **Date**: Transaction date (defaults to today)
   - **Description**: Brief description of the income

#### Optional Fields

- **Tags**: Add searchable tags for better organization
- **Category**: Select or create an income category
- **Payer**: Choose a customer from your contacts
- **Reference**: Add transaction ID, check number, etc.
- **Payment Method**: Select payment method (cash, credit card, etc.)

## Income Categories

#### Managing Categories

1. Go to **Settings → Income Categories**
2. Add new categories as needed
3. Use categories to:
   - Track different revenue streams
   - Generate filtered reports
   - Analyze income patterns

## Real-Time Balance Calculation

The system automatically calculates your account balance using the formula:

```
Current Balance = (Initial Balance + Total Income) - Total Expenses
```

## Example:

- Initial Balance: $120.00
- New Income: $400.00
- Expense: $10.00
- Current Balance: ($120.00 + $400.00) - $10.00 = $510.00

## Multi-Currency Support

- System automatically converts transactions to your home currency
- Exchange rates are applied based on your settings
- View balances in both original and home currency

## Income Reports

Access detailed income reports through:

1. **Reports → Income Reports**
2. **Reports → Income vs Expense**
3. **Reports → Reports by Date**

## Report Features

- Filter by date range
- Sort by category
- Export to CSV/PDF
- Compare with previous periods
- View trends and patterns

## Best Practices

1. **Regular Recording**
   
   - Record income transactions promptly
   - Maintain accurate dates for proper accounting

2. **Proper Categorization**
   
   - Use specific categories for different income sources
   - Maintain consistent categorization for accurate reporting

3. **Documentation**
   
   - Attach relevant files to income entries
   - Add detailed descriptions for future reference

4. **Reconciliation**
   
   - Regularly compare system balances with bank statements
   - Address any discrepancies promptly

## API Integration

For developers: Use the API to automate income recording:

```php
$ch = curl_init();
curl_setopt($ch, CURLOPT_URL, 'https://your-domain.com/?api_key=YOUR_API_KEY&ng=api/v2/income');
curl_setopt($ch, CURLOPT_POST, 1);
curl_setopt($ch, CURLOPT_POSTFIELDS, [
    'amount' => 1000,
    'description' => 'Monthly Service Fee',
    'date' => '2024-11-16',
    'category' => 'Services'
]);
$response = curl_exec($ch);
```