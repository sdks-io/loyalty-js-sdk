
# Error Info

*This model accepts additional fields of type unknown.*

## Structure

`ErrorInfo`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `user` | [`ErrorPresenter`](../../doc/models/error-presenter.md) | Required | - |
| `developer` | [`ErrorPresenter \| undefined`](../../doc/models/error-presenter.md) | Optional | - |
| `additionalProperties` | `Record<string, unknown>` | Optional | - |

## Example

```ts
import { ErrorInfo } from 'shell-loyalty-sdk';

const errorInfo: ErrorInfo = {
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
};
```

