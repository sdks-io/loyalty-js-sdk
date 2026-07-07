
# Currency Data

currencyData is only filled, where there is possible non-same currency cross-border transaction

*This model accepts additional fields of type unknown.*

## Structure

`CurrencyData`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `code` | `string` | Required | Currency code |
| `symbol` | `string` | Required | Currency symbol |
| `isSuffix` | `boolean` | Required | Currency format (is the symbol after the value) |
| `hasSpace` | `boolean` | Required | Currency format (is there a space between the symbol and the value) |
| `additionalProperties` | `Record<string, unknown>` | Optional | - |

## Example

```ts
import { CurrencyData } from 'shell-loyalty-sdk';

const currencyData: CurrencyData = {
  code: 'USD',
  symbol: '$',
  isSuffix: false,
  hasSpace: false,
  additionalProperties: {
    'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
  },
};
```

