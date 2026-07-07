
# Fault Detail

*This model accepts additional fields of type unknown.*

## Structure

`FaultDetail`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `errorcode` | `string \| undefined` | Optional | The error code. |
| `additionalProperties` | `Record<string, unknown>` | Optional | - |

## Example

```ts
import { FaultDetail } from 'shell-loyalty-sdk';

const faultDetail: FaultDetail = {
  errorcode: 'The request contains bad syntax or cannot be fulfilled.',
  additionalProperties: {
    'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
  },
};
```

