
# Error Source

*This model accepts additional fields of type unknown.*

## Structure

`ErrorSource`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `pointer` | `string \| undefined` | Optional | - |
| `additionalProperties` | `Record<string, unknown>` | Optional | - |

## Example

```ts
import { ErrorSource } from 'loyalty-sdk';

const errorSource: ErrorSource = {
  pointer: 'pointer4',
  additionalProperties: {
    'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
  },
};
```

