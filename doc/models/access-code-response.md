
# Access Code Response

*This model accepts additional fields of type unknown.*

## Structure

`AccessCodeResponse`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `accessCode` | `string \| undefined` | Optional | AccessCode provided by Shell after it redirects the user to the partner's URL. |
| `expiresIn` | `number \| undefined` | Optional | Indicates the number of seconds until the accessCode expires |
| `additionalProperties` | `Record<string, unknown>` | Optional | - |

## Example

```ts
import { AccessCodeResponse } from 'loyalty-sdk';

const accessCodeResponse: AccessCodeResponse = {
  accessCode: 'AAAAAAAAAAAAA',
  expiresIn: 30,
  additionalProperties: {
    'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
  },
};
```

