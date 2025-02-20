# FouzderIT Business Suite API Documentation

## Overview

The FouzderIT Business Suite API provides a secure and flexible way to integrate your business systems with FouzderIT. This RESTful API enables you to programmatically access and manage your business data, automate workflows, and build custom integrations.

## API Basics

### Base URL

    https://your-domain.com/api/v2/
    

### Authentication

#### Admin API Authentication

    # Using Bearer Token
    Authorization: Bearer your-api-key-here
    
    # Alternative Query String Method
    https://your-domain.com/?api_key=your-api-key-here&ng=api/v2/endpoint
    

#### 
1.  Navigate to `Settings → API Access`
2.  Create a new API key by providing a label
3.  Store the generated key securely

### Response Format

All API responses are returned in JSON format:

    {
        "success": true,
        "data": {
            
        },
        "message": "Optional status message"
    }
    

#### Error Response Format

    {
        "success": false,
        "errors": {
            "field_name": "Error description"
        },
        "message": "Error message"
    }
    

## Quick Start Guide

### 1\. Basic Authentication Example

    <?php
    // PHP Example
    $ch = curl_init();
    curl_setopt($ch, CURLOPT_URL, 'https://your-domain.com/api/v2/customers');
    curl_setopt($ch, CURLOPT_RETURNTRANSFER, true);
    curl_setopt($ch, CURLOPT_HTTPHEADER, [
        'Authorization: Bearer your-api-key-here',
        'Content-Type: application/json'
    ]);
    $response = curl_exec($ch);
    curl_close($ch);
    

    // JavaScript Example
    fetch('https://your-domain.com/api/v2/customers', {
        headers: {
            'Authorization': 'Bearer your-api-key-here',
            'Content-Type': 'application/json'
        }
    })
    .then(response => response.json())
    .then(data => console.log(data));
    

### 2\. Basic Data Retrieval

    # Get all customers
    GET /api/v2/customers
    
    # Get specific customer
    GET /api/v2/customers/{id}
    
    # Get all invoices
    GET /api/v2/invoices
    

### 3\. Creating Data

    # Create a new customer
    POST /api/v2/customers
    Content-Type: application/json
    
    {
        "account": "John Doe",
        "email": "john@example.com",
        "phone": "1234567890"
    }
    

## Available Endpoints

### Core Endpoints

-   `/customers` - Customer management
-   `/invoices` - Invoice operations
-   `/transactions` - Financial transactions
-   `/quotes` - Quote management
-   `/products` - Product catalog
-   `/orders` - Order processing

### Additional Endpoints

-   `/leads` - Lead management
-   `/suppliers` - Supplier operations
-   `/purchases` - Purchase orders
-   `/tickets` - Support tickets

## Rate Limiting

The API implements rate limiting to ensure system stability:

-   1000 requests per hour per API key
-   Rate limit headers included in responses

    X-RateLimit-Limit: 1000
    X-RateLimit-Remaining: 999
    X-RateLimit-Reset: 1516131220
    

## Security Best Practices

### API Key Protection

-   Never expose API keys in client-side code
-   Rotate keys periodically
-   Use environment variables for key storage
-   Implement key-specific permissions

### HTTPS

-   Always use HTTPS for API requests
-   Verify SSL certificates
-   Keep security libraries updated

## Common Use Cases

### 1\. Customer Integration

    // Create new customer
    $customer_data = [
        'account' => 'Jane Doe',
        'email' => 'jane@example.com',
        'phone' => '1234567890'
    ];
    
    $response = api_post('customers', $customer_data);
    

### 2\. Invoice Generation

    // Create new invoice
    $invoice_data = [
        'customer_id' => 123,
        'items' => [
            [
                'description' => 'Product A',
                'amount' => 100.00,
                'qty' => 1
            ]
        ]
    ];
    
    $response = api_post('invoices', $invoice_data);
    

## Development Tools

### PHP SDK

Official SDK libraries available in Github

## Error Handling

### Common HTTP Status Codes

-   `200` - Success
-   `201` - Created
-   `400` - Bad Request
-   `401` - Unauthorized
-   `403` - Forbidden
-   `404` - Not Found
-   `429` - Too Many Requests
-   `500` - Server Error

### Error Response Example

    {
        "success": false,
        "errors": {
            "email": "Invalid email format"
        },
        "message": "Validation failed"
    }