
# Sale Item Product

*This model accepts additional fields of type unknown.*

## Structure

`SaleItemProduct`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `id` | `string` | Required | Unique Id of the product |
| `name` | `string` | Required | Name of the product |
| `productType` | [`ProductType`](../../doc/models/product-type.md) | Required | Indicating the Type of the product (Fuel, CR, CC, PARTNER, OTHER, GREEN_ENERGY). |
| `productCode` | `string \| undefined` | Optional | Product code of gift item (euroShell Forward Code). To be populated with 3 digit Euroshell product code. |
| `productDescription` | `string \| undefined` | Optional | - |
| `additionalProductDescription` | `string \| undefined` | Optional | Customer name of the product provided by the partner<br><br>**Constraints**: *Maximum Length*: `100` |
| `additionalProperties` | `Record<string, unknown>` | Optional | - |

## Example

```ts
import { ProductType, SaleItemProduct } from 'loyalty-sdk';

const saleItemProduct: SaleItemProduct = {
  id: '31AS2434',
  name: 'Ferrari Umbrella',
  productType: ProductType.Partner,
  productCode: 'productCode4',
  productDescription: 'productDescription0',
  additionalProductDescription: 'King Guest Room',
  additionalProperties: {
    'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
  },
};
```

