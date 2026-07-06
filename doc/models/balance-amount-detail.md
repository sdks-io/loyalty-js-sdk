
# Balance Amount Detail

*This model accepts additional fields of type unknown.*

## Structure

`BalanceAmountDetail`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `amount` | `number` | Required | Current value of specified balance. |
| `state` | [`BalanceState`](../../doc/models/balance-state.md) | Required | State of the points balance amount.<br><br>**Constraints**: *Minimum Length*: `1` |
| `dateTime` | `string` | Required | Expiration Date in JSON recommended format: “yyyy-MM-ddTHH:mm:ssZ” Nullable. |
| `dateTimestamp` | `bigint` | Required | Date as Unix epoch (UTC). |
| `cashAmount` | `number \| undefined` | Optional | Point to cash exchange amnount. |
| `period` | `number \| undefined` | Optional | Period of expiration, minimum value is 1. Seralized only when it’s not null.<br><br>**Constraints**: `>= 1` |
| `position` | `number[] \| undefined` | Optional | The list of numbers describes an index of boost’s position in qualifying visit, Seralized only when it’s not null and not empty.<br><br>**Constraints**: *Unique Items Required* |
| `additionalProperties` | `Record<string, unknown>` | Optional | - |

## Example

```ts
import { BalanceAmountDetail, BalanceState } from 'loyalty-sdk';

const balanceAmountDetail: BalanceAmountDetail = {
  amount: 5,
  state: BalanceState.Available,
  dateTime: '2022-02-25T15:16:29Z',
  dateTimestamp: BigInt(1645802189000),
  cashAmount: 7.5,
  period: 1,
  position: [
    237,
    238,
    239
  ],
  additionalProperties: {
    'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
  },
};
```

