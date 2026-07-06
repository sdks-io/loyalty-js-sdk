
# Voucher Item

*This model accepts additional fields of type unknown.*

## Structure

`VoucherItem`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `code` | `string` | Required | Voucher code |
| `expiryDate` | `bigint` | Required | Expiry date as Unix epoch (UTC), as requested by MobGen. |
| `expiryDateTimestamp` | `string` | Required | Expiry date in JSON recommended format: “yyyy-MM-ddTHH:mm:ssZ” |
| `additionalProperties` | `Record<string, unknown>` | Optional | - |

## Example

```ts
import { VoucherItem } from 'loyalty-sdk';

const voucherItem: VoucherItem = {
  code: 'test123',
  expiryDate: BigInt(166),
  expiryDateTimestamp: '2022-01-30T12:35:15Z',
  additionalProperties: {
    'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
  },
};
```

