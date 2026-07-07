
# Offer

*This model accepts additional fields of type unknown.*

## Structure

`Offer`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `offerId` | `bigint` | Required | Offer ID provided upon offer configuration |
| `referenceId` | `string` | Required | Unique Reference ID for the transaction from the partner. Used to identify duplicate requests.<br><br>**Constraints**: *Maximum Length*: `128` |
| `title` | `string` | Required | Title of the partner's offer, given upon configuration<br><br>**Constraints**: *Maximum Length*: `4000` |
| `description` | `string` | Required | Description of the partner's offer, set up upon offer configuration<br><br>**Constraints**: *Maximum Length*: `4000` |
| `validFrom` | `string` | Required | Offer validity start date in JSON recommended format: "yyyy-MM-ddTHH:mm:ssZ".<br><br>The date format must follow ISO_8601. If 'Z' is written immediately after the time, it is considered UTC.<br><br>Time offset from UTC can be appended instead of 'Z' using plus or minus signs. Negative UTC offsets describe a time zone west of UTC�00:00, where the civil time is behind (or earlier) than UTC. Positive UTC offsets describe a time zone east of UTC�00:00, where the civil time is ahead (or later) than UTC |
| `validTo` | `string \| null \| undefined` | Optional | Offer validity end date in JSON recommended format: "yyyy-MM-ddTHH:mm:ssZ".<br><br>The date format must follow ISO_8601. If 'Z' is written immediately after the time, it is considered UTC.<br><br>Time offset from UTC can be appended instead of 'Z' using plus or minus signs. Negative UTC offsets describe a time zone west of UTC�00:00, where the civil time is behind (or earlier) than UTC. Positive UTC offsets describe a time zone east of UTC�00:00, where the civil time is ahead (or later) than UTC<br><br>Nullable field value, in case of the offer has infinite valid to. |
| `additionalProperties` | `Record<string, unknown>` | Optional | - |

## Example

```ts
import { Offer } from 'shell-loyalty-sdk';

const offer: Offer = {
  offerId: BigInt(5231933),
  referenceId: 'as3df5131fas3f54f92h5df',
  title: 'Partner\'s offer title',
  description: 'Buy 1 get 2',
  validFrom: '2021-03-08T17:12:55Z',
  validTo: '2021-03-08T17:12:55Z',
  additionalProperties: {
    'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
  },
};
```

