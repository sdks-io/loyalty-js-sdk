
# Transaction Balance Amount

*This model accepts additional fields of type unknown.*

## Structure

`TransactionBalanceAmount`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `amount` | `number` | Required | Current value of specified balance |
| `state` | [`TransactionBalanceState`](../../doc/models/transaction-balance-state.md) | Required | State of the amount |
| `additionalProperties` | `Record<string, unknown>` | Optional | - |

## Example

```ts
import {
  TransactionBalanceAmount,
  TransactionBalanceState,
} from 'shell-loyalty-sdk';

const transactionBalanceAmount: TransactionBalanceAmount = {
  amount: 25.56,
  state: TransactionBalanceState.Available,
  additionalProperties: {
    'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
  },
};
```

