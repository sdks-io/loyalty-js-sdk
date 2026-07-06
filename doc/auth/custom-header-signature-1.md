
# Custom Header Signature



Documentation for accessing and setting credentials for PrivateBasicToken.

## Auth Credentials

| Name | Type | Description | Setter |
|  --- | --- | --- | --- |
| Public Basic Token | `string` | - | `publicBasicToken` |



**Note:** Auth credentials can be set using `privateBasicTokenCredentials` object in the client.

## Usage Example

### Client Initialization

You must provide credentials in the client as shown in the following code snippet.

```ts
import { Client } from 'loyalty-sdk';

const client = new Client({
  privateBasicTokenCredentials: {
    'Public Basic Token': 'Public Basic Token'
  },
});
```


