
# Balance Amount

List of Balances for the customer

*This model accepts additional fields of type unknown.*

## Structure

`BalanceAmount`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `amounts` | [`BalanceCurrencyAmount[] \| undefined`](../../doc/models/balance-currency-amount.md) | Optional | **Constraints**: *Minimum Items*: `1`, *Unique Items Required* |
| `additionalProperties` | `Record<string, unknown>` | Optional | - |

## Example

```ts
import {
  BalanceAmount,
  BalanceCurrencyType,
  BalanceState,
} from 'loyalty-sdk';

const balanceAmount: BalanceAmount = {
  amounts: [
    {
      currencyType: BalanceCurrencyType.Stamp,
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
    },
    {
      currencyType: BalanceCurrencyType.Stamp,
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
    },
    {
      currencyType: BalanceCurrencyType.Stamp,
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
    }
  ],
  additionalProperties: {
    'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
  },
};
```

