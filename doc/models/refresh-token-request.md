
# Refresh Token Request

*This model accepts additional fields of type unknown.*

## Structure

`RefreshTokenRequest`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `refreshToken` | `string` | Required | The refresh token which was provided from the exchangeAccessCode end point. |
| `additionalProperties` | `Record<string, unknown>` | Optional | - |

## Example

```ts
import { RefreshTokenRequest } from 'loyalty-sdk';

const refreshTokenRequest: RefreshTokenRequest = {
  refreshToken: 'refreshToken4',
  additionalProperties: {
    'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
  },
};
```

