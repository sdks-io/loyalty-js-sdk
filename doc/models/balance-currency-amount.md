
# Balance Currency Amount

*This model accepts additional fields of type unknown.*

## Structure

`BalanceCurrencyAmount`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `currencyType` | [`BalanceCurrencyType`](../../doc/models/balance-currency-type.md) | Required | **Constraints**: *Minimum Length*: `1` |
| `amounts` | [`BalanceAmountDetail[] \| undefined`](../../doc/models/balance-amount-detail.md) | Optional | **Constraints**: *Minimum Items*: `1`, *Unique Items Required* |
| `additionalProperties` | `Record<string, unknown>` | Optional | - |

## Example

```ts
import {
  BalanceCurrencyAmount,
  BalanceCurrencyType,
  BalanceState,
} from 'shell-loyalty-sdk';

const balanceCurrencyAmount: BalanceCurrencyAmount = {
  currencyType: BalanceCurrencyType.Point,
  amounts: [
    {
      amount: 104.18,
      state: BalanceState.TotalSpent,
      dateTime: '2016-03-13T12:52:32.123Z',
      dateTimestamp: BigInt(110),
      cashAmount: 243.86,
      period: 224,
      position: [
        181,
        182,
        183
      ],
      additionalProperties: {
        'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
      },
    },
    {
      amount: 104.18,
      state: BalanceState.TotalSpent,
      dateTime: '2016-03-13T12:52:32.123Z',
      dateTimestamp: BigInt(110),
      cashAmount: 243.86,
      period: 224,
      position: [
        181,
        182,
        183
      ],
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

