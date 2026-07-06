
# Transaction Balance State

State of the amount

## Enumeration

`TransactionBalanceState`

## Fields

| Name |
|  --- |
| `Available` |
| `Expiring` |
| `Reserved` |
| `Target` |
| `Boost` |
| `Change` |
| `TotalSpent` |
| `Earned` |
| `Redeemed` |

## Example

```ts
import { TransactionBalanceState } from 'loyalty-sdk';

const transactionBalanceState = TransactionBalanceState.Redeemed;
```

