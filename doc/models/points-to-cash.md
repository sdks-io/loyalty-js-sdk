
# Points to Cash

*This model accepts additional fields of type unknown.*

## Structure

`PointsToCash`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `pointsRedeemed` | `number \| undefined` | Optional | The points used for converting it to cash |
| `totalAmount` | `number \| undefined` | Optional | Total amount in cash used |
| `pointsToCashMop` | `boolean \| undefined` | Optional | Indication if the p2c was used as a method of payment |
| `additionalProperties` | `Record<string, unknown>` | Optional | - |

## Example

```ts
import { PointsToCash } from 'shell-loyalty-sdk';

const pointsToCash: PointsToCash = {
  pointsRedeemed: 88.32,
  totalAmount: 108.04,
  pointsToCashMop: true,
  additionalProperties: {
    'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
  },
};
```

