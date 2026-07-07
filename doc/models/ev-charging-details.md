
# Ev Charging Details

*This model accepts additional fields of type unknown.*

## Structure

`EvChargingDetails`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `chargePointSerialId` | `string` | Required | Charging point serial ID |
| `chargePointConnectorTypeCd` | `string \| undefined` | Optional | Charging point connector type |
| `chargePointConnectorTypeDesc` | `string \| undefined` | Optional | Charging point connector description |
| `startDateTime` | `string` | Required | Date and time at which the transaction started. Format as per ISO 8601 standard. |
| `endDateTime` | `string` | Required | Date and time at which the transaction ended. Format as per ISO 8601 standard. |
| `duration` | `number` | Required | Duration of the transaction in seconds.<br><br>**Default**: `0` |
| `additionalProperties` | `Record<string, unknown>` | Optional | - |

## Example

```ts
import { EvChargingDetails } from 'shell-loyalty-sdk';

const evChargingDetails: EvChargingDetails = {
  chargePointSerialId: 'chargePointSerialId8',
  startDateTime: '2022-08-24T12:35:15Z',
  endDateTime: '2022-08-24T12:54:15Z',
  duration: 0,
  chargePointConnectorTypeCd: 'chargePointConnectorTypeCd6',
  chargePointConnectorTypeDesc: 'chargePointConnectorTypeDesc2',
  additionalProperties: {
    'exampleAdditionalProperty': { 'key1': 'val1', 'key2': 'val2' }
  },
};
```

