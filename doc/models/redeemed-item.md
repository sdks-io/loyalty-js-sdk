
# Redeemed Item

*This model accepts additional fields of type unknown.*

## Structure

`RedeemedItem`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `description` | `string \| undefined` | Optional | Description - currently not in use |
| `amount` | `number` | Required | Total amount |
| `detailType` | [`TransactionDetailType`](../../doc/models/transaction-detail-type.md) | Required | Indicates the Type of the transaction detail row (award, redemption, transfer, voucher, refund or central award). |
| `discountAmount` | `number` | Required | Discount amount of sales line |
| `offerInfos` | [`OfferInfo[]`](../../doc/models/offer-info.md) | Required | - |
| `offerLang` | [`OfferLanguage \| undefined`](../../doc/models/offer-language.md) | Optional | - |
| `originalAmount` | `number` | Required | Original amount of sales line |
| `productData` | [`RedeemedItemProduct`](../../doc/models/redeemed-item-product.md) | Required | - |
| `quantity` | `number` | Required | Quantity of product |
| `vatAmount` | `number \| undefined` | Optional | Value added tax |
| `vatRate` | `number \| undefined` | Optional | VAT rate of sales line |
| `points` | `number \| undefined` | Optional | Number of points redeemed. Applicable for redeemedItems and not for saleItems |
| `vouchers` | `string[] \| undefined` | Optional | List of vouchers |
| `voucherItems` | [`VoucherItem[] \| undefined`](../../doc/models/voucher-item.md) | Optional | - |
| `additionalProperties` | `Record<string, unknown>` | Optional | - |

## Example

```ts
import {
  ProductType,
  RedeemedItem,
  TransactionDetailType,
} from 'shell-loyalty-sdk';

const redeemedItem: RedeemedItem = {
  amount: 172.08,
  detailType: TransactionDetailType.Redemption,
  discountAmount: 45.58,
  offerInfos: [
    {
      discountValue: 53.28,
      loyaltyOfferId: '1234567890123',
      reason: '10% Off on fuel',
      loyaltyOfferAmount: 134,
      loyaltyOfferCode: 'loyaltyOfferCode2',
      loyaltyOfferDescription: 'loyaltyOfferDescription2',
      loyaltyOfferType: 'loyaltyOfferType0',
      loyaltySchemeCode: 'loyaltySchemeCode4',
      additionalProperties: {
        'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
      },
    }
  ],
  originalAmount: 32.5,
  productData: {
    id: '31AS2434',
    name: 'Ferrari Umbrella',
    productType: ProductType.Partner,
    reasonForRedemption: 'Burgers',
    productCode: 'productCode4',
    productDescription: 'productDescription0',
    additionalProperties: {
      'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
    },
  },
  quantity: 122.02,
  description: 'description6',
  offerLang: {
    id: 'id8',
    title: 'title6',
    description: 'description2',
    customText: 'customText2',
    additionalProperties: {
      'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
    },
  },
  vatAmount: 154.38,
  vatRate: 139.42,
  points: 122,
  additionalProperties: {
    'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
  },
};
```

