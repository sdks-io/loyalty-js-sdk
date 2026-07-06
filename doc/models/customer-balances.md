
# Customer Balances

*This model accepts additional fields of type unknown.*

## Structure

`CustomerBalances`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `balances` | [`BalanceAmount[] \| undefined`](../../doc/models/balance-amount.md) | Optional | A list of points balances. Not nullable, an empty array is used instead.<br><br>**Constraints**: *Minimum Items*: `0` |
| `additionalProperties` | `Record<string, unknown>` | Optional | - |

## Example

```ts
import {
  BalanceCurrencyType,
  BalanceState,
  CustomerBalances,
} from 'loyalty-sdk';

const customerBalances: CustomerBalances = {
  balances: [
    {
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
    },
    {
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
    }
  ],
  additionalProperties: {
    'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
  },
};
```

