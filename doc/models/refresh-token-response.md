
# Refresh Token Response

*This model accepts additional fields of type unknown.*

## Structure

`RefreshTokenResponse`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `accessToken` | `string` | Required | - |
| `refreshToken` | `string` | Required | - |
| `expiresIn` | `number` | Required | Indicates the number of seconds until the new access token provided in the pair expires |
| `additionalProperties` | `Record<string, unknown>` | Optional | - |

## Example

```ts
import { RefreshTokenResponse } from 'shell-loyalty-sdk';

const refreshTokenResponse: RefreshTokenResponse = {
  accessToken: 'accessToken2',
  refreshToken: 'refreshToken2',
  expiresIn: 84,
  additionalProperties: {
    'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
  },
};
```

