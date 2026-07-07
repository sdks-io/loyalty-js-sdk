
# Client Auth Token Request

## Structure

`ClientAuthTokenRequest`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `clientId` | `string` | Required | Client ID provided by Shell |
| `clientSecret` | `string` | Required | Client Secret provided by Shell |
| `grantType` | `string` | Required | Grant type value for access<br><br>**Constraints**: *Maximum Length*: `20` |

## Example

```ts
import { ClientAuthTokenRequest } from 'shell-loyalty-sdk';

const clientAuthTokenRequest: ClientAuthTokenRequest = {
  clientId: 'twuwywTYUHAH6AHHJ',
  clientSecret: 'yuahaYThdvdowoUUU7wjsjMM',
  grantType: 'client_credentials',
};
```

