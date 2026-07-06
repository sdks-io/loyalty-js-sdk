
# Transactions Response

*This model accepts additional fields of type unknown.*

## Structure

`TransactionsResponse`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `totalResults` | `number` | Required | Total no of resource which will be sent back across all pages |
| `nextPage` | `string` | Required | API URI which must be used to retrieve the next page of resources |
| `previousPage` | `string` | Required | API URI which must be used to retrieve the previous page of resources |
| `totalSaved` | `number` | Required | Total amount saved so far |
| `transactions` | [`Transaction[]`](../../doc/models/transaction.md) | Required | Transactions list |
| `additionalProperties` | `Record<string, unknown>` | Optional | - |

## Example

```ts
import {
  ProductType,
  TransactionDetailType,
  TransactionsResponse,
  UnitMeasure,
} from 'loyalty-sdk';

const transactionsResponse: TransactionsResponse = {
  totalResults: 80,
  nextPage: '.../nextpage',
  previousPage: '.../previouspage',
  totalSaved: 227.3,
  transactions: [
    {
      transactionDateTime: BigInt(194),
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
      totalAmount: 94.62,
      totalDiscountAmount: 120.32,
      totalDiscountedFullAmount: 122.62,
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
    }
  ],
  additionalProperties: {
    'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
  },
};
```

