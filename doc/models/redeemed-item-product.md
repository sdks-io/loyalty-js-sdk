
# Redeemed Item Product

*This model accepts additional fields of type unknown.*

## Structure

`RedeemedItemProduct`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `id` | `string` | Required | Unique Id of the product |
| `name` | `string` | Required | Name of the product |
| `productType` | [`ProductType`](../../doc/models/product-type.md) | Required | Indicating the Type of the product (Fuel, CR, CC, PARTNER, OTHER, GREEN_ENERGY). |
| `reasonForRedemption` | `string \| undefined` | Optional | Reason for redemption of points as mentioned by the partner. reasonForRedemption to be populated only for redeemedItems (not for saleItems) when productType = PARTNER. |
| `productCode` | `string \| undefined` | Optional | Product code of gift item (euroShell Forward Code). To be populated with 3 digit Euroshell product code. |
| `productDescription` | `string \| undefined` | Optional | - |
| `additionalProperties` | `Record<string, unknown>` | Optional | - |

## Example

```ts
import { ProductType, RedeemedItemProduct } from 'shell-loyalty-sdk';

const redeemedItemProduct: RedeemedItemProduct = {
  id: '31AS2434',
  name: 'Ferrari Umbrella',
  productType: ProductType.Partner,
  reasonForRedemption: 'Burgers',
  productCode: 'productCode4',
  productDescription: 'productDescription0',
  additionalProperties: {
    'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
  },
};
```

