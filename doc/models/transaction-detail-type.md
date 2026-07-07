
# Transaction Detail Type

Indicates the Type of the transaction detail row (award, redemption, transfer, voucher, refund or central award).

## Enumeration

`TransactionDetailType`

## Fields

| Name |
|  --- |
| `Award` |
| `Redemption` |
| `Transfer` |
| `Refund` |
| `CentralAward` |
| `Voucher` |

## Example

```ts
import { TransactionDetailType } from 'shell-loyalty-sdk';

const transactionDetailType = TransactionDetailType.Transfer;
```

