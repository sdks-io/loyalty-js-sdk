
# Redemption Response Item

*This model accepts additional fields of type unknown.*

## Structure

`RedemptionResponseItem`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `itemId` | `string \| undefined` | Optional | Unique Item ID for the transaction from the partner. Used to identify the catalogue item in the Shell Loyalty Platform. Each Partner will have one or more items set up in the Shell Loyalty Platform. |
| `quantity` | `number \| undefined` | Optional | The quantity of the items required. |
| `points` | `number \| undefined` | Optional | The number of points that will be redemmed from the Shell Loyalty Platform. |
| `reasonForRedemption` | `string \| undefined` | Optional | The reason for the points redemption. This attribute will be shown in the Transaction History feture. |
| `additionalProperties` | `Record<string, unknown>` | Optional | - |

## Example

```ts
import { RedemptionResponseItem } from 'loyalty-sdk';

const redemptionResponseItem: RedemptionResponseItem = {
  itemId: '1005',
  quantity: 2,
  points: 50,
  reasonForRedemption: 'ChesseBurger',
  additionalProperties: {
    'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
  },
};
```

