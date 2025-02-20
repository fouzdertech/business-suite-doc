# API Endpoints Reference

## Core Resources

### Customers

#### List All Customers

    GET /api/v2/customers
    

**Parameters:**

-   `page` (optional) - Page number for pagination
-   `limit` (optional) - Results per page (default: 20)
-   `search` (optional) - Search term for filtering

**Response:**

    {
        "success": true,
        "data": [
            {
                "id": 1,
                "account": "John Doe",
                "email": "john@example.com",
                "phone": "1234567890",
                "created_at": "2024-01-15T10:00:00Z",
                "updated_at": "2024-01-15T10:00:00Z"
            }
        ],
        "meta": {
            "current_page": 1,
            "total_pages": 5,
            "total_records": 100
        }
    }
    

#### Create Customer

    POST /api/v2/customers
    

**Request Body:**

    {
        "account": "Jane Smith",
        "email": "jane@example.com",
        "phone": "1234567890",
        "address": "123 Business St",
        "city": "New York",
        "state": "NY",
        "zip": "10001",
        "country": "US"
    }
    

#### Get Customer

    GET /api/v2/customers/{id}
    

#### Update Customer

    PUT /api/v2/customers/{id}
    

#### Delete Customer

    DELETE /api/v2/customers/{id}
    

### Invoices

#### List All Invoices

    GET /api/v2/invoices
    

**Parameters:**

-   `status` (optional) - Filter by status (Paid, Unpaid, Partially Paid)
-   `customer_id` (optional) - Filter by customer
-   `date_from` (optional) - Start date
-   `date_to` (optional) - End date

**Response:**

    {
        "success": true,
        "data": [
            {
                "id": 1,
                "invoice_number": "INV-2024-001",
                "customer_id": 1,
                "amount": 1500.00,
                "status": "Unpaid",
                "due_date": "2024-02-15",
                "items": [
                    {
                        "description": "Web Development",
                        "amount": 1500.00,
                        "qty": 1
                    }
                ]
            }
        ]
    }
    

#### Create Invoice

    POST /api/v2/invoices
    

**Request Body:**

    {
        "customer_id": 1,
        "date": "2024-01-15",
        "due_date": "2024-02-15",
        "items": [
            {
                "description": "Web Development",
                "amount": 1500.00,
                "qty": 1
            }
        ],
        "notes": "Payment due within 30 days"
    }
    

### Transactions

#### List Transactions

    GET /api/v2/transactions
    

**Parameters:**

-   `type` (optional) - Income/Expense
-   `account_id` (optional) - Filter by account
-   `date_from` (optional) - Start date
-   `date_to` (optional) - End date

#### Record Transaction

    POST /api/v2/transactions
    

**Request Body:**

    {
        "type": "Income",
        "account_id": 1,
        "amount": 1500.00,
        "category_id": 1,
        "description": "Website Development Payment",
        "date": "2024-01-15"
    }
    

### Products/Services

#### List Products

    GET /api/v2/products
    

#### Create Product

    POST /api/v2/products
    

**Request Body:**

    {
        "name": "Web Hosting",
        "price": 99.99,
        "description": "Annual web hosting package",
        "type": "service",
        "tax_rate": 10
    }
    

### Quotes

#### List Quotes

    GET /api/v2/quotes
    

#### Create Quote

    POST /api/v2/quotes
    

**Request Body:**

    {
        "customer_id": 1,
        "valid_until": "2024-02-15",
        "items": [
            {
                "description": "Consulting Services",
                "amount": 2000.00,
                "qty": 1
            }
        ]
    }
    

## Support Resources

### Tickets

#### List Tickets

    GET /api/v2/tickets
    

**Parameters:**

-   `status` (optional) - Open/Closed/Pending
-   `department_id` (optional) - Filter by department

#### Create Ticket

    POST /api/v2/tickets
    

**Request Body:**

    {
        "customer_id": 1,
        "subject": "Technical Support Required",
        "message": "Need assistance with installation",
        "department_id": 1,
        "priority": "High"
    }
    

### Leads

#### Create Lead

    POST /api/v2/leads
    

**Request Body:**

    {
        "first_name": "John",
        "last_name": "Smith",
        "email": "john@example.com",
        "company": "Acme Corp",
        "phone": "1234567890",
        "source": "Website"
    }
    

## Administrative Endpoints

### Users

#### List Users

    GET /api/v2/users
    

#### Create User

    POST /api/v2/users
    

**Request Body:**

    {
        "name": "Admin User",
        "email": "admin@example.com",
        "password": "securepassword",
        "role": "administrator"
    }
    

### Reports

#### Financial Summary

    GET /api/v2/reports/financial
    

**Parameters:**

-   `year` (optional) - Filter by year
-   `month` (optional) - Filter by month

**Response:**

    {
        "success": true,
        "data": {
            "income": 15000.00,
            "expenses": 5000.00,
            "profit": 10000.00,
            "outstanding_invoices": 3000.00
        }
    }
    

## Webhook Notifications

### Register Webhook

    POST /api/v2/webhooks
    

**Request Body:**

    {
        "url": "https://your-domain.com/webhook",
        "events": ["invoice.created", "payment.received"]
    }
    

## Batch Operations

### Batch Create Customers

    POST /api/v2/batch/customers
    

**Request Body:**

    {
        "customers": [
            {
                "account": "Customer 1",
                "email": "customer1@example.com"
            },
            {
                "account": "Customer 2",
                "email": "customer2@example.com"
            }
        ]
    }
    

## Error Responses

### Validation Error

    {
        "success": false,
        "errors": {
            "email": "Invalid email format",
            "amount": "Amount must be greater than 0"
        },
        "message": "Validation failed"
    }
    

### Authentication Error

    {
        "success": false,
        "message": "Invalid API key or unauthorized access"
    }
    

## Rate Limiting

All endpoints are subject to rate limiting:

-   1000 requests per hour per API key
-   Rate limit headers included in responses

    X-RateLimit-Limit: 1000
    X-RateLimit-Remaining: 999
    X-RateLimit-Reset: 1516131220
    

## Best Practices

### Endpoint Usage

1.  Always include error handling
2.  Implement pagination for list endpoints
3.  Use appropriate HTTP methods
4.  Cache responses when possible

### Security

1.  Keep API keys secure
2.  Use HTTPS for all requests
3.  Implement request signing
4.  Monitor API usage

## Testing

### Sandbox Environment

-   Use prefix: `https://sandbox.your-domain.com/api/v2/`
-   Test credentials provided separately
-   Reset data daily

### Response Codes

-   `200` - Success
-   `201` - Created
-   `400` - Bad Request
-   `401` - Unauthorized
-   `403` - Forbidden
-   `404` - Not Found
-   `429` - Too Many Requests
-   `500` - Server Error