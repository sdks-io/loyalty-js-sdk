
# Json Api Version

*This model accepts additional fields of type unknown.*

## Structure

`JsonApiVersion`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `version` | `string \| undefined` | Optional | - |
| `additionalProperties` | `Record<string, unknown>` | Optional | - |

## Example

```ts
import { JsonApiVersion } from 'shell-loyalty-sdk';

const jsonApiVersion: JsonApiVersion = {
  version: 'version6',
  additionalProperties: {
    'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
  },
};
```

