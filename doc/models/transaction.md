
# Transaction

*This model accepts additional fields of type unknown.*

## Structure

`Transaction`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `transactionDateTime` | `bigint` | Required | Transaction date as Unix epoch (UTC), as requested by MobGen. |
| `transactionDateTimeStamp` | `string \| undefined` | Optional | Transaction date in JSON recommended format: “yyyy-MM-ddTHH:mm:ssZ” |
| `siteData` | [`SiteData`](../../doc/models/site-data.md) | Required | - |
| `loyalty` | [`LoyaltyCardInfo`](../../doc/models/loyalty-card-info.md) | Required | - |
| `transactionId` | `string \| undefined` | Optional | Unique Id of the transaction row. |
| `partnerCode` | `string \| undefined` | Optional | Unique code identifying the partner |
| `partnerName` | `string \| undefined` | Optional | Name of the partner |
| `partnerLogo` | `string \| undefined` | Optional | - |
| `referenceId` | `string \| undefined` | Optional | Reference ID for each transaction. It is unique for each partner and transaction. |
| `totalAmount` | `number` | Required | Total amount of the transaction. |
| `totalDiscountAmount` | `number` | Required | Total discount amount of the transaction. |
| `totalDiscountedFullAmount` | `number` | Required | totalAmount - totalDiscountedFullAmount |
| `totalVatAmount` | `number \| undefined` | Optional | Total amount of VAT |
| `balances` | [`TransactionBalance[] \| undefined`](../../doc/models/transaction-balance.md) | Optional | - |
| `currencyCode` | `string \| undefined` | Optional | Currency using ISO4217 alpha-3 currency code |
| `saleItems` | [`SaleItem[]`](../../doc/models/sale-item.md) | Required | - |
| `redeemedItems` | [`RedeemedItem[]`](../../doc/models/redeemed-item.md) | Required | - |
| `transactionVouchers` | [`TransactionVoucher[]`](../../doc/models/transaction-voucher.md) | Required | - |
| `receiptNumber` | `string \| undefined` | Optional | Unique number of transaction's receipt |
| `pointsToCash` | [`PointsToCash \| undefined`](../../doc/models/points-to-cash.md) | Optional | - |
| `companyId` | `bigint \| undefined` | Optional | Partner identifier |
| `isPartnerRedemption` | `boolean \| undefined` | Optional | Describes whether the transaction is partner redemption. |
| `currencyData` | [`CurrencyData \| undefined`](../../doc/models/currency-data.md) | Optional | currencyData is only filled, where there is possible non-same currency cross-border transaction |
| `additionalProperties` | `Record<string, unknown>` | Optional | - |

## Example

```ts
import {
  ProductType,
  Transaction,
  TransactionDetailType,
  UnitMeasure,
} from 'shell-loyalty-sdk';

const transaction: Transaction = {
  transactionDateTime: BigInt(168),
  siteData: {
    countryCode: 'GB',
    siteId: '23St34',
    name: 'Shell Liphook North',
    postcode: 'GU30 7TT',
    city: 'Liphook',
    address: 'A3 T North',
    additionalProperties: {
      'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
    },
  },
  loyalty: {
    loyaltyCard: '1234567890123456789',
    additionalProperties: {
      'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
    },
  },
  totalAmount: 96.12,
  totalDiscountAmount: 118.82,
  totalDiscountedFullAmount: 124.12,
  saleItems: [
    {
      amount: 33.74,
      detailType: TransactionDetailType.Redemption,
      discountAmount: 163.24,
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
      originalAmount: 150.16,
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
      quantity: 239.68,
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
      originalNetAmount: 53.92,
      vatAmount: 36.72,
      vatRate: 1.08,
      unitMeasure: UnitMeasure.Litre,
      additionalProperties: {
        'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
      },
    }
  ],
  redeemedItems: [
    {
      amount: 7.62,
      detailType: TransactionDetailType.Redemption,
      discountAmount: 137.12,
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
      originalAmount: 124.04,
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
      quantity: 213.56,
      description: 'description0',
      offerLang: {
        id: 'id8',
        title: 'title6',
        description: 'description2',
        customText: 'customText2',
        additionalProperties: {
          'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
        },
      },
      vatAmount: 62.84,
      vatRate: 230.96,
      points: 60,
      additionalProperties: {
        'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
      },
    }
  ],
  transactionVouchers: [
    {
      detailType: TransactionDetailType.Redemption,
      code: '5000000100071',
      name: 'Ferrari Umbrella',
      amount: 8.04,
      quantity: 213.98,
      additionalProperties: {
        'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
      },
    }
  ],
  transactionDateTimeStamp: '2022-01-21T12:35:15Z',
  transactionId: '8435166weew2332w',
  partnerCode: 'GB10CMLP_RAC',
  partnerName: 'RAC',
  partnerLogo: 'https://www.shell.co.uk/1234.jpg',
  referenceId: 'abcde12345xyz',
  currencyCode: 'GBP',
  receiptNumber: '18a6sdf8a63448612',
  isPartnerRedemption: true,
  additionalProperties: {
    'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
  },
};
```

