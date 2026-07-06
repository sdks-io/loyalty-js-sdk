
# Custom Header Signature



Documentation for accessing and setting credentials for PublicBasicToken.

## Auth Credentials

| Name | Type | Description | Setter |
|  --- | --- | --- | --- |
| Public Basic Token | `string` | - | `publicBasicToken` |



**Note:** Auth credentials can be set using `publicBasicTokenCredentials` object in the client.

## Usage Example

### Client Initialization

You must provide credentials in the client as shown in the following code snippet.

```ts
import { Client } from 'loyalty-sdk';

const client = new Client({
  publicBasicTokenCredentials: {
    'Public Basic Token': 'Public Basic Token'
  },
});
```


