
# Resource Not Found Error

*This model accepts additional fields of type unknown.*

## Structure

`ResourceNotFoundError`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `errorCode` | `number` | Required | HTTP error status code |
| `message` | `string` | Required | HTTP error status message |
| `error` | [`ErrorInfo`](../../doc/models/error-info.md) | Required | - |
| `additionalProperties` | `Record<string, unknown>` | Optional | - |

## Example

```ts
try {
  // make the API call
} catch (error) {
  if (error instanceof ResourceNotFoundError) {
    console.log(error.result);
  }
}
```

