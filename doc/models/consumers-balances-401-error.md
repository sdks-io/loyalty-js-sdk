
# Consumers Balances 401 Error

*This model accepts additional fields of type unknown.*

## Structure

`ConsumersBalances401Error`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `errorCode` | `number` | Required | - |
| `message` | `string` | Required | - |
| `error` | `unknown` | Required | - |
| `additionalProperties` | `Record<string, unknown>` | Optional | - |

## Example

```ts
try {
  // make the API call
} catch (error) {
  if (error instanceof ConsumersBalances401Error) {
    console.log(error.result);
  }
}
```

