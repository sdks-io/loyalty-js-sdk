
# Getting Started with Loyalty APIs

## Introduction

Loyalty Account Management provides the end points needed in order to generate the user Authorization Tokens which will provide access to the Loyalty APIs and also to update the user profile.

## Install the Package

Run the following command from your project directory to install the package from npm:

```bash
npm install loyalty-sdk@0.0.4
```

For additional package details, see the [Npm page for the loyalty-sdk@0.0.4 npm](https://www.npmjs.com/package/loyalty-sdk/v/0.0.4).

## Initialize the API Client

**_Note:_** Documentation for the client can be found [here.](https://www.github.com/sdks-io/loyalty-js-sdk/tree/0.0.4/doc/client.md)

The following parameters are configurable for the API Client:

| Parameter | Type | Description |
|  --- | --- | --- |
| environment | [`Environment`](https://www.github.com/sdks-io/loyalty-js-sdk/tree/0.0.4/README.md#environments) | The API environment. <br> **Default: `Environment.Sit`** |
| timeout | `number` | Timeout for API calls.<br>*Default*: `30000` |
| httpClientOptions | [`Partial<HttpClientOptions>`](https://www.github.com/sdks-io/loyalty-js-sdk/tree/0.0.4/doc/http-client-options.md) | Stable configurable http client options. |
| unstableHttpClientOptions | `any` | Unstable configurable http client options. |
| logging | [`PartialLoggingOptions`](https://www.github.com/sdks-io/loyalty-js-sdk/tree/0.0.4/doc/partial-logging-options.md) | Logging Configuration to enable logging |
| publicBearerTokenCredentials | [`PublicBearerTokenCredentials`](https://www.github.com/sdks-io/loyalty-js-sdk/tree/0.0.4/doc/auth/oauth-2-bearer-token.md) | The credential object for publicBearerToken |
| publicBasicTokenCredentials | [`PublicBasicTokenCredentials`](https://www.github.com/sdks-io/loyalty-js-sdk/tree/0.0.4/doc/auth/custom-header-signature.md) | The credential object for publicBasicToken |
| privateBasicTokenCredentials | [`PrivateBasicTokenCredentials`](https://www.github.com/sdks-io/loyalty-js-sdk/tree/0.0.4/doc/auth/custom-header-signature-1.md) | The credential object for privateBasicToken |
| clientAuthorizationTokenCredentials | [`ClientAuthorizationTokenCredentials`](https://www.github.com/sdks-io/loyalty-js-sdk/tree/0.0.4/doc/auth/oauth-2-client-credentials-grant.md) | The credential object for clientAuthorizationToken |
| customerHeaderCredentials | [`CustomerHeaderCredentials`](https://www.github.com/sdks-io/loyalty-js-sdk/tree/0.0.4/doc/auth/custom-header-signature-2.md) | The credential object for customerHeader |

The API client can be initialized as follows:

### Code-Based Client Initialization

```ts
import { Client, Environment, LogLevel } from 'loyalty-sdk';

const client = new Client({
  publicBearerTokenCredentials: {
    accessToken: 'AccessToken'
  },
  publicBasicTokenCredentials: {
    'Public Basic Token': 'Public Basic Token'
  },
  privateBasicTokenCredentials: {
    'Public Basic Token': 'Public Basic Token'
  },
  clientAuthorizationTokenCredentials: {
    oauthClientId: 'OAuthClientId',
    oauthClientSecret: 'OAuthClientSecret'
  },
  customerHeaderCredentials: {
    'Authorization-Token': 'Authorization-Token'
  },
  timeout: 30000,
  environment: Environment.Sit,
  logging: {
    logLevel: LogLevel.Info,
    logRequest: {
      logBody: true
    },
    logResponse: {
      logHeaders: true
    }
  },
});
```

### Configuration-Based Client Initialization

```ts
import * as path from 'path';
import * as fs from 'fs';
import { Client } from 'loyalty-sdk';

// Provide absolute path for the configuration file
const absolutePath = path.resolve('./config.json');

// Read the configuration file content
const fileContent = fs.readFileSync(absolutePath, 'utf-8');

// Initialize client from JSON configuration content
const client = Client.fromJsonConfig(fileContent);
```

See the [Configuration-Based Client Initialization](https://www.github.com/sdks-io/loyalty-js-sdk/tree/0.0.4/doc/configuration-based-client-initialization.md) section for details.

### Environment-Based Client Initialization

```ts
import * as dotenv from 'dotenv';
import * as path from 'path';
import * as fs from 'fs';
import { Client } from 'loyalty-sdk';

// Optional - Provide absolute path for the .env file
const absolutePath = path.resolve('./.env');

if (fs.existsSync(absolutePath)) {
  // Load environment variables from .env file
  dotenv.config({ path: absolutePath, override: true });
}

// Initialize client using environment variables
const client = Client.fromEnvironment(process.env);
```

See the [Environment-Based Client Initialization](https://www.github.com/sdks-io/loyalty-js-sdk/tree/0.0.4/doc/environment-based-client-initialization.md) section for details.

## Environments

The SDK can be configured to use a different environment for making API calls. Available environments are:

### Fields

| Name | Description |
|  --- | --- |
| Sit | **Default** |
| Production | - |
| Uat | - |

## Authorization

This API uses the following authentication schemes.

* [`PublicBearerToken (OAuth 2 Bearer token)`](https://www.github.com/sdks-io/loyalty-js-sdk/tree/0.0.4/doc/auth/oauth-2-bearer-token.md)
* [`PublicBasicToken (Custom Header Signature)`](https://www.github.com/sdks-io/loyalty-js-sdk/tree/0.0.4/doc/auth/custom-header-signature.md)
* [`PrivateBasicToken (Custom Header Signature)`](https://www.github.com/sdks-io/loyalty-js-sdk/tree/0.0.4/doc/auth/custom-header-signature-1.md)
* [`client-authorization-token (OAuth 2 Client Credentials Grant)`](https://www.github.com/sdks-io/loyalty-js-sdk/tree/0.0.4/doc/auth/oauth-2-client-credentials-grant.md)
* [`customerHeader (Custom Header Signature)`](https://www.github.com/sdks-io/loyalty-js-sdk/tree/0.0.4/doc/auth/custom-header-signature-2.md)

## List of APIs

* [Profile Management](https://www.github.com/sdks-io/loyalty-js-sdk/tree/0.0.4/doc/controllers/profile-management.md)
* [Authorization](https://www.github.com/sdks-io/loyalty-js-sdk/tree/0.0.4/doc/controllers/authorization.md)
* [Offer](https://www.github.com/sdks-io/loyalty-js-sdk/tree/0.0.4/doc/controllers/offer.md)
* [Balances](https://www.github.com/sdks-io/loyalty-js-sdk/tree/0.0.4/doc/controllers/balances.md)
* [Redemption](https://www.github.com/sdks-io/loyalty-js-sdk/tree/0.0.4/doc/controllers/redemption.md)
* [Transaction](https://www.github.com/sdks-io/loyalty-js-sdk/tree/0.0.4/doc/controllers/transaction.md)

## SDK Infrastructure

### Configuration

* [HttpClientOptions](https://www.github.com/sdks-io/loyalty-js-sdk/tree/0.0.4/doc/http-client-options.md)
* [RetryConfiguration](https://www.github.com/sdks-io/loyalty-js-sdk/tree/0.0.4/doc/retry-configuration.md)
* [ProxySettings](https://www.github.com/sdks-io/loyalty-js-sdk/tree/0.0.4/doc/proxy-settings.md)
* [Configuration-Based Client Initialization](https://www.github.com/sdks-io/loyalty-js-sdk/tree/0.0.4/doc/configuration-based-client-initialization.md)
* [Environment-Based Client Initialization](https://www.github.com/sdks-io/loyalty-js-sdk/tree/0.0.4/doc/environment-based-client-initialization.md)
* [PartialLoggingOptions](https://www.github.com/sdks-io/loyalty-js-sdk/tree/0.0.4/doc/partial-logging-options.md)
* [PartialRequestLoggingOptions](https://www.github.com/sdks-io/loyalty-js-sdk/tree/0.0.4/doc/partial-request-logging-options.md)
* [PartialResponseLoggingOptions](https://www.github.com/sdks-io/loyalty-js-sdk/tree/0.0.4/doc/partial-response-logging-options.md)
* [LoggerInterface](https://www.github.com/sdks-io/loyalty-js-sdk/tree/0.0.4/doc/logger-interface.md)

### HTTP

* [HttpRequest](https://www.github.com/sdks-io/loyalty-js-sdk/tree/0.0.4/doc/http-request.md)

### Utilities

* [ApiResponse](https://www.github.com/sdks-io/loyalty-js-sdk/tree/0.0.4/doc/api-response.md)
* [ApiError](https://www.github.com/sdks-io/loyalty-js-sdk/tree/0.0.4/doc/api-error.md)

