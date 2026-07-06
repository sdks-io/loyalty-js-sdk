
# Transaction Balance

*This model accepts additional fields of type unknown.*

## Structure

`TransactionBalance`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `currencyType` | [`TransactionCurrencyType`](../../doc/models/transaction-currency-type.md) | Required | Type of balance |
| `amounts` | [`TransactionBalanceAmount[]`](../../doc/models/transaction-balance-amount.md) | Required | - |
| `additionalProperties` | `Record<string, unknown>` | Optional | - |

## Example

```ts
import {
  TransactionBalance,
  TransactionBalanceState,
  TransactionCurrencyType,
} from 'loyalty-sdk';

const transactionBalance: TransactionBalance = {
  currencyType: TransactionCurrencyType.Airmiles,
  amounts: [
    {
      amount: 104.18,
      state: TransactionBalanceState.Available,
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

