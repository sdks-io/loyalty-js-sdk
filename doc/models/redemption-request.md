
# Redemption Request

*This model accepts additional fields of type unknown.*

## Structure

`RedemptionRequest`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `uuid` | `string` | Required | The SSO uuid of the user signed in with Shell credentials.<br>Format: 32 hexadecimal digits grouped the following way: xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx<br>See: https://www.wikiwand.com/en/Universally_unique_identifier#/Format |
| `referenceId` | `string` | Required | A unique ID for the transaction from the partner. Used to identify duplicate requests.<br><br>**Constraints**: *Maximum Length*: `128` |
| `redemptionReqArray` | [`RedemptionItem[]`](../../doc/models/redemption-item.md) | Required | Specifies the number of points to be redeemed from the user's point balance and the reason for redemption, which will also be shown to the user. Mutiple redemption items can be submitted in a single API request. |
| `additionalProperties` | `Record<string, unknown>` | Optional | - |

## Example

```ts
import { RedemptionRequest } from 'loyalty-sdk';

const redemptionRequest: RedemptionRequest = {
  uuid: 'cee1157e-cac0-4fc6-b92b-68a13b456b43',
  referenceId: 'as3df5131fas3f54f92h5df',
  redemptionReqArray: [
    {
      itemId: '1005',
      points: 50,
      reasonForRedemption: 'Cheeseburger',
      quantity: 2,
      additionalProperties: {
        'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
      },
    },
    {
      itemId: '1006',
      points: 20,
      reasonForRedemption: 'Chips',
      quantity: 1,
      additionalProperties: {
        'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
      },
    },
    {
      itemId: '1007',
      points: 10,
      reasonForRedemption: 'Ice Cream',
      quantity: 220,
      additionalProperties: {
        'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
      },
    }
  ],
  additionalProperties: {
    'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
  },
};
```

