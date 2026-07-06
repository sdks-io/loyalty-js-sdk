
# Json Api Error

*This model accepts additional fields of type unknown.*

## Structure

`JsonApiError`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `jsonapi` | [`JsonApiVersion \| undefined`](../../doc/models/json-api-version.md) | Optional | - |
| `errors` | [`ErrorItem[] \| undefined`](../../doc/models/error-item.md) | Optional | - |
| `additionalProperties` | `Record<string, unknown>` | Optional | - |

## Example

```ts
try {
  // make the API call
} catch (error) {
  if (error instanceof JsonApiError) {
    console.log(error.result);
  }
}
```

