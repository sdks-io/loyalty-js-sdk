
# Fault

*This model accepts additional fields of type unknown.*

## Structure

`Fault`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `faultstring` | `string \| undefined` | Optional | The description of the error. |
| `detail` | [`FaultDetail \| undefined`](../../doc/models/fault-detail.md) | Optional | - |
| `additionalProperties` | `Record<string, unknown>` | Optional | - |

## Example

```ts
import { Fault } from 'loyalty-sdk';

const fault: Fault = {
  faultstring: 'Bad Request',
  detail: {
    errorcode: 'errorcode6',
    additionalProperties: {
      'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
    },
  },
  additionalProperties: {
    'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
  },
};
```

