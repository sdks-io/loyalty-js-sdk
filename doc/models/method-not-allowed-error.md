
# Method Not Allowed Error

An error response.

## Structure

`MethodNotAllowedError`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `fault` | [`Fault \| undefined`](../../doc/models/fault.md) | Optional | - |

## Example

```ts
import { MethodNotAllowedError } from 'shell-loyalty-sdk';

const methodNotAllowedError: MethodNotAllowedError = {
  fault: {
    faultstring: 'faultstring2',
    detail: {
      errorcode: 'errorcode6',
      additionalProperties: {
        'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
      },
    },
    additionalProperties: {
      'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
    },
  },
};
```

