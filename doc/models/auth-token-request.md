
# Auth Token Request

*This model accepts additional fields of type unknown.*

## Structure

`AuthTokenRequest`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `digest` | `string \| undefined` | Optional | - |
| `additionalProperties` | `Record<string, unknown>` | Optional | - |

## Example

```ts
import { AuthTokenRequest } from 'loyalty-sdk';

const authTokenRequest: AuthTokenRequest = {
  digest: 'Aaaaaaaaaaaaaa',
  additionalProperties: {
    'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
  },
};
```

