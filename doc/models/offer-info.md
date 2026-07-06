
# Offer Info

*This model accepts additional fields of type unknown.*

## Structure

`OfferInfo`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `discountValue` | `number` | Required | Discount value of the offer |
| `loyaltyOfferAmount` | `number \| undefined` | Optional | Total amount of points awarded for the given product code. |
| `loyaltyOfferCode` | `string \| undefined` | Optional | Unique ID of the voucher/coupon. |
| `loyaltyOfferDescription` | `string \| undefined` | Optional | Name of loyalty offer |
| `loyaltyOfferId` | `string` | Required | Loyalty Offer ID |
| `loyaltyOfferType` | `string \| undefined` | Optional | Loyalty offer type |
| `loyaltySchemeCode` | `string \| undefined` | Optional | Loyalty Scheme code |
| `reason` | `string` | Required | Offer/reward name |
| `additionalProperties` | `Record<string, unknown>` | Optional | - |

## Example

```ts
import { OfferInfo } from 'loyalty-sdk';

const offerInfo: OfferInfo = {
  discountValue: 14.12,
  loyaltyOfferId: '1234567890123',
  reason: '10% Off on fuel',
  loyaltyOfferAmount: 58,
  loyaltyOfferCode: 'loyaltyOfferCode8',
  loyaltyOfferDescription: 'loyaltyOfferDescription6',
  loyaltyOfferType: 'loyaltyOfferType4',
  loyaltySchemeCode: 'loyaltySchemeCode8',
  additionalProperties: {
    'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
  },
};
```

