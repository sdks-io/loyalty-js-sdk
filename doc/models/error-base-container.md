
# Error Base Container

*This model accepts additional fields of type unknown.*

## Structure

`ErrorBaseContainer`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `user` | [`ErrorPresenter`](../../doc/models/error-presenter.md) | Required | - |
| `developer` | [`ErrorPresenter`](../../doc/models/error-presenter.md) | Required | - |
| `additionalProperties` | `Record<string, unknown>` | Optional | - |

## Example

```ts
import { ErrorBaseContainer } from 'shell-loyalty-sdk';

const errorBaseContainer: ErrorBaseContainer = {
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
  additionalProperties: {
    'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
  },
};
```

