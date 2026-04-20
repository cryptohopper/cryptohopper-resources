# Getting Started with the Cryptohopper API

The Cryptohopper API is a REST API that allows developers to programmatically interact with the Cryptohopper platform. You can manage trading bots, retrieve trade and position data, configure strategies, and integrate Cryptohopper functionality into custom applications and workflows.

## API Overview

The Cryptohopper API provides endpoints for:

- **Hopper management**: Create, configure, and control trading bots.
- **Trade data**: Retrieve open positions, trade history, and portfolio information.
- **Strategy configuration**: Get and update strategy settings.
- **Marketplace**: Access marketplace data and subscriptions.
- **Account management**: Manage account settings and subscriptions.

## Base URL

All API requests are made to:

```
https://api.cryptohopper.com/v1
```

## Authentication

The Cryptohopper API uses **OAuth2** for authentication. You need to register an application, obtain client credentials, and use the authorization flow to get access tokens. See the [Authentication guide](authentication.md) for the full OAuth2 flow.

## Quick Start

### Step 1: Register Your Application
Register your application on the Cryptohopper platform to receive a **client ID** and **client secret**. These credentials identify your application when making API requests.

### Step 2: Authenticate
Implement the OAuth2 authorization code flow to obtain an access token. This token is included in the `Authorization` header of every API request.

```
Authorization: Bearer YOUR_ACCESS_TOKEN
```

### Step 3: Make Your First API Call
With a valid access token, you can make API requests. For example, to retrieve a list of your hoppers:

```
GET https://api.cryptohopper.com/v1/hopper
Authorization: Bearer YOUR_ACCESS_TOKEN
```

The response contains a JSON object with your hopper data.

## Rate Limits

The Cryptohopper API enforces rate limits to ensure platform stability. Key points:

- Rate limits are applied per access token.
- Exceeding the rate limit returns a `429 Too Many Requests` response.
- Include retry logic in your application to handle rate limit responses gracefully.
- Use exponential backoff when retrying failed requests.

Check the official API documentation for current rate limit thresholds.

## Response Format

All API responses are returned in JSON format. A typical successful response:

```json
{
  "data": {
    "id": 12345,
    "name": "My Trading Bot",
    "enabled": true
  }
}
```

Error responses include an error code and message:

```json
{
  "error": {
    "code": 401,
    "message": "Unauthorized"
  }
}
```

## Common Use Cases

### Bot Management
Automate the creation and configuration of trading bots. Useful for managing multiple bots or integrating bot management into a custom dashboard.

### Performance Tracking
Pull trade data and portfolio information to build custom analytics, reporting dashboards, or performance tracking tools.

### Custom Integrations
Integrate Cryptohopper with other platforms, alerting systems, or trading tools to create automated workflows.

### Signal Delivery
Programmatically send trading signals to your bots via the API or webhooks. See the [Webhooks guide](webhooks.md) for more on signal delivery.

## Official API Documentation

For the complete API reference including all endpoints, request/response schemas, and examples, visit the official documentation:

**[Cryptohopper API Reference](https://www.cryptohopper.com/api-documentation/api-reference)**

## Next Steps

- [Authentication](authentication.md) -- Learn how to implement OAuth2 and obtain access tokens.
- [Webhooks](webhooks.md) -- Send trading signals to your bots via HTTP webhooks.
