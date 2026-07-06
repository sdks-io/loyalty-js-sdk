
# Unauthorized Error

The application is not authorised to use the requested grant type.

## Structure

`UnauthorizedError`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `fault` | [`Fault \| undefined`](../../doc/models/fault.md) | Optional | - |

## Example

```ts
import { UnauthorizedError } from 'loyalty-sdk';

const unauthorizedError: UnauthorizedError = {
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

