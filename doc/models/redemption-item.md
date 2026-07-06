
# Redemption Item

*This model accepts additional fields of type unknown.*

## Structure

`RedemptionItem`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `itemId` | `string` | Required | The itemID identifies the catalogue item in the loyalty system. Shell will set these up and share the IDs with the partner. |
| `quantity` | `number \| undefined` | Optional | Number of items redeemed on the user's behalf. If the quantity is not specified, the system will assume a default quantity of 1. This is not used for the calculation of points, but only for displaying to the user.<br><br>**Default**: `1` |
| `points` | `number` | Required | Total number of points to be redeemed from the Shell Loyalty Platform for this item. |
| `reasonForRedemption` | `string` | Required | Reason for the points redemption. This attribute will be shown to the customer via app/web channel under Transaction History.<br><br>**Constraints**: *Maximum Length*: `65` |
| `additionalProperties` | `Record<string, unknown>` | Optional | - |

## Example

```ts
import { RedemptionItem } from 'loyalty-sdk';

const redemptionItem: RedemptionItem = {
  itemId: '1001',
  points: 12,
  reasonForRedemption: 'burger',
  quantity: 5,
  additionalProperties: {
    'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
  },
};
```

