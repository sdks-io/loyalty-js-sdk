
# Error Item

*This model accepts additional fields of type unknown.*

## Structure

`ErrorItem`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `status` | `number \| undefined` | Optional | - |
| `title` | `string \| undefined` | Optional | - |
| `source` | [`ErrorSource \| undefined`](../../doc/models/error-source.md) | Optional | - |
| `detail` | `string \| undefined` | Optional | - |
| `additionalProperties` | `Record<string, unknown>` | Optional | - |

## Example

```ts
import { ErrorItem } from 'loyalty-sdk';

const errorItem: ErrorItem = {
  status: 222,
  title: 'title4',
  source: {
    pointer: 'pointer6',
    additionalProperties: {
      'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
    },
  },
  detail: 'detail4',
  additionalProperties: {
    'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
  },
};
```

