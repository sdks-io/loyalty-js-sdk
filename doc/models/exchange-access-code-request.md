
# Exchange Access Code Request

*This model accepts additional fields of type unknown.*

## Structure

`ExchangeAccessCodeRequest`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `accessCode` | `string \| undefined` | Optional | AccessCode provided by Shell after it redirects the user to the partner's URL. |
| `additionalProperties` | `Record<string, unknown>` | Optional | - |

## Example

```ts
import { ExchangeAccessCodeRequest } from 'shell-loyalty-sdk';

const exchangeAccessCodeRequest: ExchangeAccessCodeRequest = {
  accessCode: 'AAAAAAAAAAAAA',
  additionalProperties: {
    'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
  },
};
```

