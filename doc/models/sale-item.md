
# Sale Item

*This model accepts additional fields of type unknown.*

## Structure

`SaleItem`

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
| `originalNetAmount` | `number \| undefined` | Optional | Original amount excluding VAT |
| `productData` | [`SaleItemProduct`](../../doc/models/sale-item-product.md) | Required | - |
| `quantity` | `number` | Required | Quantity of product |
| `vatAmount` | `number \| undefined` | Optional | Value added tax |
| `vatRate` | `number \| undefined` | Optional | VAT rate of sales line |
| `voucherItems` | [`VoucherItem[] \| undefined`](../../doc/models/voucher-item.md) | Optional | - |
| `vouchers` | `string[] \| undefined` | Optional | List of vouchers |
| `unitPrice` | `number \| undefined` | Optional | Unit price of sale item |
| `unitMeasure` | [`UnitMeasure \| undefined`](../../doc/models/unit-measure.md) | Optional | Unit of measure |
| `ev` | [`EvChargingDetails \| undefined`](../../doc/models/ev-charging-details.md) | Optional | - |
| `points` | `number \| undefined` | Optional | Points earned in a transaction |
| `additionalProperties` | `Record<string, unknown>` | Optional | - |

## Example

```ts
import {
  ProductType,
  SaleItem,
  TransactionDetailType,
  UnitMeasure,
} from 'shell-loyalty-sdk';

const saleItem: SaleItem = {
  amount: 61.72,
  detailType: TransactionDetailType.Redemption,
  discountAmount: 191.22,
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
  originalAmount: 178.14,
  productData: {
    id: '31AS2434',
    name: 'Ferrari Umbrella',
    productType: ProductType.Partner,
    productCode: 'productCode4',
    productDescription: 'productDescription0',
    additionalProductDescription: 'King Guest Room',
    additionalProperties: {
      'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
    },
  },
  quantity: 11.66,
  description: 'Not in use',
  offerLang: {
    id: 'id8',
    title: 'title6',
    description: 'description2',
    customText: 'customText2',
    additionalProperties: {
      'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
    },
  },
  originalNetAmount: 81.9,
  vatAmount: 8.74,
  vatRate: 29.06,
  unitMeasure: UnitMeasure.Litre,
  additionalProperties: {
    'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
  },
};
```

