# Cryptohopper API Authentication: OAuth2 Guide

The Cryptohopper API uses OAuth2 for authentication and authorization. This guide explains how to register your application, authenticate users, obtain access tokens, and manage token lifecycles.

## OAuth2 Overview

OAuth2 is an industry-standard authorization framework that allows third-party applications to access Cryptohopper resources on behalf of a user without requiring the user's password. Instead, the user grants your application permission through a secure authorization flow, and your application receives tokens to make API requests.

## Step 1: Register Your Application

Before using the API, register your application on the Cryptohopper platform:

1. Log in to your Cryptohopper account.
2. Navigate to the API/Developer section.
3. Register a new application.
4. Provide a **redirect URI** -- the URL where users will be sent after authorizing your application.
5. Receive your **client ID** and **client secret**.

Store your client secret securely. Never expose it in client-side code or public repositories.

## Step 2: Authorization Code Flow

The authorization code flow is the recommended method for server-side applications.

### 2a: Redirect User to Authorization

Direct the user to the Cryptohopper authorization endpoint:

```
GET https://www.cryptohopper.com/oauth2/authorize
  ?client_id=YOUR_CLIENT_ID
  &redirect_uri=YOUR_REDIRECT_URI
  &response_type=code
  &scope=read write
```

**Parameters:**
- `client_id` -- Your application's client ID.
- `redirect_uri` -- Must match the redirect URI registered with your application.
- `response_type` -- Set to `code` for the authorization code flow.
- `scope` -- The permissions your application is requesting (space-separated).

### 2b: User Grants Permission

The user logs in to Cryptohopper (if not already logged in) and is presented with a consent screen showing the permissions your application is requesting. If the user approves, they are redirected to your redirect URI with an authorization code.

```
GET YOUR_REDIRECT_URI?code=AUTHORIZATION_CODE
```

### 2c: Exchange Authorization Code for Tokens

Your server exchanges the authorization code for an access token and refresh token:

```
POST https://www.cryptohopper.com/oauth2/token
Content-Type: application/x-www-form-urlencoded

grant_type=authorization_code
&code=AUTHORIZATION_CODE
&client_id=YOUR_CLIENT_ID
&client_secret=YOUR_CLIENT_SECRET
&redirect_uri=YOUR_REDIRECT_URI
```

**Response:**

```json
{
  "access_token": "eyJhbGciOi...",
  "refresh_token": "dGhpcyBpcy...",
  "token_type": "Bearer",
  "expires_in": 86400
}
```

## Access Tokens

The access token is used to authenticate API requests. Include it in the `Authorization` header:

```
Authorization: Bearer YOUR_ACCESS_TOKEN
```

### Token Expiration
Access tokens expire after a set period (indicated by `expires_in` in seconds). Once expired, API requests will return a `401 Unauthorized` response. Use the refresh token to obtain a new access token.

## Refresh Tokens

Refresh tokens are long-lived tokens used to obtain new access tokens without requiring the user to re-authorize your application.

### Refreshing an Access Token

```
POST https://www.cryptohopper.com/oauth2/token
Content-Type: application/x-www-form-urlencoded

grant_type=refresh_token
&refresh_token=YOUR_REFRESH_TOKEN
&client_id=YOUR_CLIENT_ID
&client_secret=YOUR_CLIENT_SECRET
```

**Response:**

```json
{
  "access_token": "new_access_token...",
  "refresh_token": "new_refresh_token...",
  "token_type": "Bearer",
  "expires_in": 86400
}
```

Store the new refresh token, as the previous one may be invalidated after use.

## Scopes

Scopes define the level of access your application has. Request only the scopes your application needs.

| Scope | Description |
|-------|-------------|
| `read` | Read access to account data, hoppers, positions, and trade history. |
| `write` | Write access to create and modify hoppers, settings, and configurations. |
| `trade` | Permission to execute trades and manage positions. |
| `notifications` | Access to notification settings and delivery. |

Request scopes during the authorization step as a space-separated list in the `scope` parameter.

## Security Best Practices

### Protect Your Client Secret
Never expose your client secret in frontend code, mobile applications, or version control. Store it securely on your server.

### Use HTTPS
Always use HTTPS for all API communications. Never send tokens or credentials over unencrypted connections.

### Validate Redirect URIs
Ensure your redirect URI matches exactly what was registered. Mismatches can indicate a security issue.

### Store Tokens Securely
Store access tokens and refresh tokens securely on your server. Use encrypted storage and limit access to authorized processes.

### Handle Token Expiration Gracefully
Implement logic to detect expired tokens (401 responses) and automatically refresh them using the refresh token. Avoid prompting users to re-authorize unnecessarily.

### Minimal Scope Requests
Request only the scopes your application needs. This follows the principle of least privilege and reduces risk.

## Error Handling

Common authentication errors:

| Error | Description |
|-------|-------------|
| `invalid_client` | The client ID or secret is incorrect. |
| `invalid_grant` | The authorization code or refresh token is invalid or expired. |
| `invalid_scope` | A requested scope is not valid. |
| `unauthorized_client` | The application is not authorized to use this grant type. |

## Next Steps

- [Getting Started](getting-started.md) -- Overview of the Cryptohopper API.
- [Webhooks](webhooks.md) -- Send trading signals via HTTP webhooks.
- [Cryptohopper API Reference](https://www.cryptohopper.com/api-documentation/api-reference) -- Full endpoint documentation.
