
# Loyalty Card Info

*This model accepts additional fields of type unknown.*

## Structure

`LoyaltyCardInfo`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `loyaltyCard` | `string \| undefined` | Optional | Loyalty card of the transaction. |
| `additionalProperties` | `Record<string, unknown>` | Optional | - |

## Example

```ts
import { LoyaltyCardInfo } from 'loyalty-sdk';

const loyaltyCardInfo: LoyaltyCardInfo = {
  loyaltyCard: '1234567890123456789',
  additionalProperties: {
    'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
  },
};
```

