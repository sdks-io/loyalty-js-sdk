
# Auth Token Response

*This model accepts additional fields of type unknown.*

## Structure

`AuthTokenResponse`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `token` | `string \| undefined` | Optional | Your Basic public token which needs to be used in the auth/ExchangeAccessCode. |
| `tokenType` | `string \| undefined` | Optional | Type of the token. |
| `expiresIn` | `string \| undefined` | Optional | With value **unlimited** it means this token will never expire |
| `owner` | `string \| undefined` | Optional | States the name of the partner to which the digest used belongs |
| `additionalProperties` | `Record<string, unknown>` | Optional | - |

## Example

```ts
import { AuthTokenResponse } from 'loyalty-sdk';

const authTokenResponse: AuthTokenResponse = {
  token: 'AhshsisaahshsuewenJJJJNFFTA',
  tokenType: 'Basic',
  expiresIn: 'unlimited',
  owner: 'partner_abc',
  additionalProperties: {
    'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
  },
};
```

