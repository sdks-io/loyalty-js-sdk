
# Error Presenter

*This model accepts additional fields of type unknown.*

## Structure

`ErrorPresenter`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `appErrorCode` | `string` | Required | custom error code for developer or user<br>Note: One of the following values will be returned:<br>1000, 1001, 1002, 1003, 1004, 1005, 1006, 1007, 1009, 1010, 1011, 1012, 1014, 1015, 1016<br><br>**Constraints**: *Maximum Length*: `10` |
| `message` | `string` | Required | Custom error message <br><br>Note: One of the following values will be returned:<br><br>- Offer does not exist<br>- Customer does not exist<br>- Valid from date is invalid<br>- ValidityPeriod is invalid<br>- Offer is by default assigned to all customers, which cannot be changed.<br>- Assignment is not allowed<br>- Customer assign should have validity dates.<br>- Customer assign validity start date should be before the validity end date.<br>- Customer assign validity dates must be between the offer assignable dates.<br>- Offer validity start date should not be in the past.<br>- Customer already assigned to this offer.<br>- Offer module is disabled<br>- Partner code is not valid for this offer<br>- Reference ID already used<br>- Partner assignment already ended for this customer<br><br>**Constraints**: *Maximum Length*: `500` |
| `reason` | `string \| null \| undefined` | Optional | reason for the error |
| `subject` | `string \| null \| undefined` | Optional | subject of the error. Examples will be shared later |
| `subjectType` | `string \| null \| undefined` | Optional | subject type of the error. Examples will be shared later. |
| `type` | `string \| null \| undefined` | Optional | Type of error. Examples will be shared later. |
| `additionalProperties` | `Record<string, unknown>` | Optional | - |

## Example

```ts
import { ErrorPresenter } from 'loyalty-sdk';

const errorPresenter: ErrorPresenter = {
  appErrorCode: '1002',
  message: 'Error message for 1002',
  reason: 'Reason of 1002',
  subject: '1002 Subject',
  subjectType: 'Error subject type',
  type: 'Unknow Type',
  additionalProperties: {
    'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
  },
};
```

