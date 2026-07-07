
# Not Found Error Response

*This model accepts additional fields of type unknown.*

## Structure

`NotFoundErrorResponse`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `errorCode` | `number` | Required | HTTP error code 404 |
| `message` | `string` | Required | HTTP error message - Not Found<br><br>**Constraints**: *Maximum Length*: `500` |
| `error` | [`ErrorInfo`](../../doc/models/error-info.md) | Required | - |
| `additionalProperties` | `Record<string, unknown>` | Optional | - |

## Example

```ts
import { NotFoundErrorResponse } from 'shell-loyalty-sdk';

const notFoundErrorResponse: NotFoundErrorResponse = {
  errorCode: 404,
  message: 'Not Found',
  error: {
    user: {
      appErrorCode: '1002',
      message: 'Error message for 1002',
      reason: 'Reason of 1002',
      subject: '1002 Subject',
      subjectType: 'Error subject type',
      type: 'Unknow Type',
      additionalProperties: {
        'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
      },
    },
    developer: {
      appErrorCode: 'appErrorCode4',
      message: 'message4',
      reason: 'reason0',
      subject: 'subject8',
      subjectType: 'subjectType6',
      type: 'type6',
      additionalProperties: {
        'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
      },
    },
    additionalProperties: {
      'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
    },
  },
  additionalProperties: {
    'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
  },
};
```

