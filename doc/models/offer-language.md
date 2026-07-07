
# Offer Language

*This model accepts additional fields of type unknown.*

## Structure

`OfferLanguage`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `id` | `string` | Required | Unique Id of the offer |
| `title` | `string` | Required | Title of the offer |
| `description` | `string` | Required | Description of the offer |
| `customText` | `string` | Required | Custom text of the offer |
| `additionalProperties` | `Record<string, unknown>` | Optional | - |

## Example

```ts
import { OfferLanguage } from 'shell-loyalty-sdk';

const offerLanguage: OfferLanguage = {
  id: '31AS2434',
  title: '10% OFF of Ferrari Umbrella',
  description: 'Description of 10% OFF of Ferrari Umbrella',
  customText: 'Custom text',
  additionalProperties: {
    'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
  },
};
```

