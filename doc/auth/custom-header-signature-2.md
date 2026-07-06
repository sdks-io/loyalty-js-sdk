
# Custom Header Signature



Documentation for accessing and setting credentials for customerHeader.

## Auth Credentials

| Name | Type | Description | Setter |
|  --- | --- | --- | --- |
| Authorization-Token | `string` | The partner's API key | `authorizationToken` |



**Note:** Auth credentials can be set using `customerHeaderCredentials` object in the client.

## Usage Example

### Client Initialization

You must provide credentials in the client as shown in the following code snippet.

```ts
import { Client } from 'loyalty-sdk';

const client = new Client({
  customerHeaderCredentials: {
    'Authorization-Token': 'Authorization-Token'
  },
});
```


