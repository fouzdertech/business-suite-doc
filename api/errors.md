# API Error Reference Guide

## Error Response Format

All API errors follow a consistent format:

    {
        "success": false,
        "errors": {
            "field_name": "Detailed error message"
        },
        "message": "General error description",
        "error_code": "ERROR_CODE"
    }
    

## HTTP Status Codes

### Overview

-   `2xx` - Successful operations
-   `4xx` - Client errors
-   `5xx` - Server errors

### Detailed Status Codes

#### Success Responses

    200 OK                - Request succeeded
    201 Created          - Resource created successfully
    204 No Content       - Request succeeded with no response body
    

#### Client Errors

    400 Bad Request      - Invalid request format or parameters
    401 Unauthorized     - Missing or invalid API key
    403 Forbidden        - Valid API key but insufficient permissions
    404 Not Found        - Resource not found
    409 Conflict         - Resource conflict (e.g., duplicate entry)
    422 Validation Error - Input validation failed
    429 Too Many        - Rate limit exceeded
    

#### Server Errors

    500 Server Error     - Internal server error
    502 Bad Gateway      - Invalid response from upstream server
    503 Service         - Service temporarily unavailable
    504 Gateway Timeout - Upstream server timeout
    

## Common Error Codes

### Authentication Errors

#### AUTH\_001 - Invalid API Key

    {
        "success": false,
        "message": "Invalid API key provided"
    }
    

### Client-Side Error Handling

#### JavaScript Example

    async function makeApiRequest() {
        try {
            const response = await fetch('api/v2/customers', {
                headers: {
                    'Authorization': `Bearer ${apiKey}`
                }
            });
            
            if (!response.ok) {
                const errorData = await response.json();
                handleApiError(errorData);
                return;
            }
            
            const data = await response.json();
            return data;
        } catch (error) {
            handleNetworkError(error);
        }
    }
    
    function handleApiError(errorData) {
        switch (errorData.error_code) {
            case 'AUTH_001':
                // Handle invalid API key
                break;
            case 'VAL_001':
                // Handle validation errors
                break;
            default:
                // Handle unknown errors
        }
    }