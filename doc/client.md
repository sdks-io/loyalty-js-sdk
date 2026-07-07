
# Client Class Documentation

The following parameters are configurable for the API Client:

| Parameter | Type | Description |
|  --- | --- | --- |
| environment | [`Environment`](../README.md#environments) | The API environment. <br> **Default: `Environment.Sit`** |
| timeout | `number` | Timeout for API calls.<br>*Default*: `30000` |
| httpClientOptions | [`Partial<HttpClientOptions>`](../doc/http-client-options.md) | Stable configurable http client options. |
| unstableHttpClientOptions | `any` | Unstable configurable http client options. |
| logging | [`PartialLoggingOptions`](../doc/partial-logging-options.md) | Logging Configuration to enable logging |
| publicBearerTokenCredentials | [`PublicBearerTokenCredentials`](auth/oauth-2-bearer-token.md) | The credential object for publicBearerToken |
| publicBasicTokenCredentials | [`PublicBasicTokenCredentials`](auth/custom-header-signature.md) | The credential object for publicBasicToken |
| privateBasicTokenCredentials | [`PrivateBasicTokenCredentials`](auth/custom-header-signature-1.md) | The credential object for privateBasicToken |
| clientAuthorizationTokenCredentials | [`ClientAuthorizationTokenCredentials`](auth/oauth-2-client-credentials-grant.md) | The credential object for clientAuthorizationToken |
| customerHeaderCredentials | [`CustomerHeaderCredentials`](auth/custom-header-signature-2.md) | The credential object for customerHeader |

The API client can be initialized as follows:

## Code-Based Client Initialization

```ts
import { Client, Environment, LogLevel } from 'shell-loyalty-sdk';

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

## Configuration-Based Client Initialization

```ts
import * as path from 'path';
import * as fs from 'fs';
import { Client } from 'shell-loyalty-sdk';

// Provide absolute path for the configuration file
const absolutePath = path.resolve('./config.json');

// Read the configuration file content
const fileContent = fs.readFileSync(absolutePath, 'utf-8');

// Initialize client from JSON configuration content
const client = Client.fromJsonConfig(fileContent);
```

See the [Configuration-Based Client Initialization](../doc/configuration-based-client-initialization.md) section for details.

## Environment-Based Client Initialization

```ts
import * as dotenv from 'dotenv';
import * as path from 'path';
import * as fs from 'fs';
import { Client } from 'shell-loyalty-sdk';

// Optional - Provide absolute path for the .env file
const absolutePath = path.resolve('./.env');

if (fs.existsSync(absolutePath)) {
  // Load environment variables from .env file
  dotenv.config({ path: absolutePath, override: true });
}

// Initialize client using environment variables
const client = Client.fromEnvironment(process.env);
```

See the [Environment-Based Client Initialization](../doc/environment-based-client-initialization.md) section for details.

