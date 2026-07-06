
# Offer Base

*This model accepts additional fields of type unknown.*

## Structure

`OfferBase`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `offerId` | `bigint` | Required | Offer ID provided upon offer configuration |
| `referenceId` | `string` | Required | Unique Reference ID for the transaction from the partner. Used to identify duplicate requests.<br><br>**Constraints**: *Maximum Length*: `128` |
| `title` | `string` | Required | Title of the partner's offer, given upon configuration<br><br>**Constraints**: *Maximum Length*: `4000` |
| `description` | `string` | Required | Description of the partner's offer, set up upon offer configuration<br><br>**Constraints**: *Maximum Length*: `4000` |
| `additionalProperties` | `Record<string, unknown>` | Optional | - |

## Example

```ts
import { OfferBase } from 'loyalty-sdk';

const offerBase: OfferBase = {
  offerId: BigInt(5231933),
  referenceId: 'as3df5131fas3f54f92h5df',
  title: 'Partner\'s offer title',
  description: 'Buy 1 get 2',
  additionalProperties: {
    'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
  },
};
```

