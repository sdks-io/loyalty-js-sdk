
# M200 User Partners

*This model accepts additional fields of type unknown.*

## Structure

`M200UserPartners`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `uuid` | `string` | Required | - |
| `userStatus` | `string` | Required | - |
| `market` | `unknown` | Required | - |
| `accessToken` | `string` | Required | - |
| `refreshToken` | `string` | Required | - |
| `additionalProperties` | `Record<string, unknown>` | Optional | - |

## Example

```ts
import { M200UserPartners } from 'shell-loyalty-sdk';

const m200UserPartners: M200UserPartners = {
  uuid: 'bb0dffbe‑95c8‑442f‑b15e‑53b8cf0a3d99',
  userStatus: 'UNVERIFIED',
  market: { 'code': 'en‑GB', 'country': 'GB' },
  accessToken: 'ACCESS_TOKEN',
  refreshToken: 'REFRESH_TOKEN',
  additionalProperties: {
    'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
  },
};
```

