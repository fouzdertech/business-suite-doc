# Managing Bank Accounts

### Overview

The bank accounts module in CloudOnex Business Suite helps you track and manage all your business bank accounts, cash accounts, and financial transactions. This guide covers everything from setting up accounts to reconciliation and reporting.

### Setting Up Bank Accounts

#### Creating a New Account

1. Navigate to **Accounting → New Account**

2. Fill in the account details:
   
   ```
   Required Fields:
   - Account Title/Name
   - Initial Balance (current balance as of today)
   
   Optional Fields:
   - Account Number
   - Bank Contact Person
   - Bank Phone Number
   - Internet Banking URL
   ```

#### Understanding Account Types

CloudOnex supports various account types:

- Checking Accounts
- Savings Accounts
- Credit Cards
- Cash Accounts
- Petty Cash
- Investment Accounts

#### Balance Management

Initial Balance Setup

```
Current Balance = (Initial Balance + Total Income) - Total Expenses

Example:
Initial Balance: $1,000
Total Income: $500
Total Expenses: $300
Current Balance = ($1,000 + $500) - $300 = $1,200
```

### Balance Tracking

The system automatically calculates:

- Opening balance
- Current balance
- Available balance
- Pending transactions
- Cleared transactions

### Recording Transactions

Adding Deposits

1. Go to **Accounting → New Deposit**
2. Required information:
   - Date
   - Amount
   - Description
   - Category (optional)
   - Payer (optional)
   - Reference number (optional)

### Recording Expenses

1. Navigate to **Accounting → New Expense**
2. Enter:
   - Date
   - Amount
   - Description
   - Category (optional)
   - Payee (optional)
   - Reference number (optional)
   - Attach receipts (optional)

### Account Transfers

To transfer between accounts:

1. Go to **Accounting → Transfer**
2. Select:
   - From Account (source)
   - To Account (destination)
   - Amount
   - Date
   - Description

### Account Reconciliation

Monthly Reconciliation Process

1. **Gather Documents**
   
   - Bank statements
   - Transaction records
   - Receipts and invoices

2. **Compare Transactions**

```
Step 1: Mark cleared transactions
Step 2: Identify pending items
Step 3: Note discrepancies
Step 4: Investigate differences
Step 5: Make adjustments
```

3. **Gather Documents**
   
   - Compare statement balance with system balance
   - Account for outstanding checks and deposits
   - Document any adjustments

### Reporting

#### Available Reports

1. **Account Summary**
   
   - Current balances
   - Transaction history
   - Income vs expenses

2. **Transaction Reports**
   
   - Daily transactions
   - Monthly summaries
   - Category-wise breakdown

3. **Cash Flow Reports**
   
   - Income trends
   - Expense patterns
   - Net cash flow

### Generating Reports

1. Navigate to **Reports → Financial Reports**
2. Select:
   - Report type
   - Date range
   - Account(s)
   - Categories (optional)

### Multi-Currency Management

#### Setting Up Multiple Currencies

1. Go to **Settings → Currencies**
2. Add currencies:
   - Currency code
   - Symbol
   - Base conversion rate