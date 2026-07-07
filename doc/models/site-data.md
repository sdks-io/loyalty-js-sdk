
# Site Data

*This model accepts additional fields of type unknown.*

## Structure

`SiteData`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `countryCode` | `string` | Required | Two character ISO 3166-1 alpha-2 country code |
| `siteId` | `string` | Required | Unique Id of the site |
| `name` | `string` | Required | Name of the site |
| `postcode` | `string \| undefined` | Optional | Postcode of the site |
| `city` | `string \| undefined` | Optional | City of the site |
| `address` | `string \| undefined` | Optional | Address of the site |
| `additionalProperties` | `Record<string, unknown>` | Optional | - |

## Example

```ts
import { SiteData } from 'shell-loyalty-sdk';

const siteData: SiteData = {
  countryCode: 'GB',
  siteId: '23St34',
  name: 'Shell Liphook North',
  postcode: 'GU30 7TT',
  city: 'Liphook',
  address: 'A3 T North',
  additionalProperties: {
    'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
  },
};
```

