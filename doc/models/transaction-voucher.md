
# Transaction Voucher

*This model accepts additional fields of type unknown.*

## Structure

`TransactionVoucher`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `detailType` | [`TransactionDetailType`](../../doc/models/transaction-detail-type.md) | Required | Indicates the Type of the transaction detail row (award, redemption, transfer, voucher, refund or central award). |
| `code` | `string` | Required | Unique code of the voucher |
| `name` | `string` | Required | Name of the voucher |
| `amount` | `number` | Required | Sum amount of the voucher |
| `quantity` | `number` | Required | Quantity of vouchers |
| `additionalProperties` | `Record<string, unknown>` | Optional | - |

## Example

```ts
import { TransactionDetailType, TransactionVoucher } from 'loyalty-sdk';

const transactionVoucher: TransactionVoucher = {
  detailType: TransactionDetailType.Redemption,
  code: '5000000100071',
  name: 'Ferrari Umbrella',
  amount: 171.58,
  quantity: 121.52,
  additionalProperties: {
    'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
  },
};
```

