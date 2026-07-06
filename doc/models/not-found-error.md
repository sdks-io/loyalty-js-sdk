
# Not Found Error

An error response.

## Structure

`NotFoundError`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `fault` | [`Fault \| undefined`](../../doc/models/fault.md) | Optional | - |

## Example

```ts
import { NotFoundError } from 'loyalty-sdk';

const notFoundError: NotFoundError = {
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

