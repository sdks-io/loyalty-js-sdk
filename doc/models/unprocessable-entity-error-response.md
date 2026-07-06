
# Unprocessable Entity Error Response

*This model accepts additional fields of type unknown.*

## Structure

`UnprocessableEntityErrorResponse`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `errorCode` | `number` | Required | HTTP error code 422 |
| `message` | `string` | Required | HTTP error message - Unprocessable entity<br><br>**Constraints**: *Maximum Length*: `500` |
| `error` | [`ErrorInfo`](../../doc/models/error-info.md) | Required | - |
| `additionalProperties` | `Record<string, unknown>` | Optional | - |

## Example

```ts
import { UnprocessableEntityErrorResponse } from 'loyalty-sdk';

const unprocessableEntityErrorResponse: UnprocessableEntityErrorResponse = {
  errorCode: 422,
  message: 'Unprocessalbe entity',
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

