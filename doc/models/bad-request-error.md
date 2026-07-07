
# Bad Request Error

Request is missing a parameter so the server cannot proceed with the request.

## Structure

`BadRequestError`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `fault` | [`Fault \| undefined`](../../doc/models/fault.md) | Optional | - |

## Example

```ts
import { BadRequestError } from 'shell-loyalty-sdk';

const badRequestError: BadRequestError = {
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

