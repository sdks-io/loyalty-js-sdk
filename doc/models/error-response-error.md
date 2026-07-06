
# Error Response Error

*This model accepts additional fields of type unknown.*

## Structure

`ErrorResponseError`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `errorCode` | `number` | Required | HTTP error code |
| `message` | `string` | Required | HTTP error status message |
| `error` | [`ErrorInfo`](../../doc/models/error-info.md) | Required | - |
| `additionalProperties` | `Record<string, unknown>` | Optional | - |

## Example

```ts
try {
  // make the API call
} catch (error) {
  if (error instanceof ErrorResponseError) {
    console.log(error.result);
  }
}
```

