# Balances

API for retrieving a customer's loyalty point balance

```ts
const balancesApi = new BalancesApi(client);
```

## Class Name

`BalancesApi`


# Get Balance by Uuid

Retrieve the customer's loyalty point balance

```ts
async getBalanceByUuid(
  languageCode: string,
  userAuthorizationToken: string,
  consumerUuid: string,
  countryCode: string,
  xCorrelationId?: string,
  channel?: AssignOfferChannel,
  application?: string,
  requestOptions?: RequestOptions
): Promise<ApiResponse<CustomerBalances>>
```

## Authentication

This endpoint requires [customerHeader](../../doc/auth/custom-header-signature-2.md) **AND** [client-authorization-token](../../doc/auth/oauth-2-client-credentials-grant.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `languageCode` | `string` | Query, Required | This is a concatenation of language in lower case as per ISO 639-1 , “-” and country code as per ISO 3166-1 alpha-2. |
| `userAuthorizationToken` | `string` | Header, Required | The value of the accessToken retrieved from the /auth/exchangeAccessCode endpoint. This is referred to as user-authorization-token where the access is provided by the end user. |
| `consumerUuid` | `string` | Header, Required | SSO uuid of the user signed in with Shell credentials Format: 32 hexadecimal digits grouped the following way: xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx |
| `countryCode` | `string` | Header, Required | The two character ISO 3166-1 alpha-2 [country code](https://www.iso.org/iso-3166-country-codes.html). |
| `xCorrelationId` | `string \| undefined` | Header, Optional | An unique ID in GUID format in order to track the request. |
| `channel` | [`AssignOfferChannel \| undefined`](../../doc/models/assign-offer-channel.md) | Header, Optional | Channel. |
| `application` | `string \| undefined` | Header, Optional | String |
| `requestOptions` | `RequestOptions \| undefined` | Optional | Pass additional request options. |

## Response Type

**200**: success

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `result` property of this instance returns the response data which is of type [`CustomerBalances`](../../doc/models/customer-balances.md).

## Example Usage

```ts
const languageCode = 'en-GB';

const userAuthorizationToken = 'Bearer asdfhalsdfheywuiryafhk';

const consumerUuid = 'cee1157e-cac0-4fc6-b92b-68a13b456b43';

const countryCode = 'GB';

const xCorrelationId = '8483a8c3-e2c7-4849-835f-8ed27e5be276';

const channel = AssignOfferChannel.Partner;

const application = 'PARTNER';

try {
  const response = await balancesApi.getBalanceByUuid(
    languageCode,
    userAuthorizationToken,
    consumerUuid,
    countryCode,
    xCorrelationId,
    channel,
    application
  );

  // Extracting fully parsed response body.
  console.log(response.result);

  // Extracting response status code.
  console.log(response.statusCode);
  // Extracting response headers.
  console.log(response.headers);
  // Extracting response body of type `string | Stream`
  console.log(response.body);
} catch (error) {
  if (error instanceof ApiError) {
    // Extracting response error status code.
    console.log(error.statusCode);
    // Extracting response error headers.
    console.log(error.headers);
    // Extracting response error body of type `string | Stream`.
    console.log(error.body);
    if (error instanceof ConsumersBalances400Error) {
      console.log(error.result);
    } else if (error instanceof ConsumersBalances401Error) {
      console.log(error.result);
    } else if (error instanceof ConsumersBalances404Error) {
      console.log(error.result);
    } else if (error instanceof ConsumersBalances422Error) {
      console.log(error.result);
    }
  }
}
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| 400 | Bad request - The request was not valid. This code is returned when the server has attempted to process the request, but some aspect of the request is not valid, for example an incorrectly formatted resource or an attempt to deploy an invalid event project to the event runtime. Information about the request is provided in the response body, and includes an error code and error message. | [`ConsumersBalances400Error`](../../doc/models/consumers-balances-400-error.md) |
| 401 | Unauthorized request, Missing Authorization header, or expired authorization token etc. It is returned from the application server<br>when application security is enabled, and authorization information was missing from the request. | [`ConsumersBalances401Error`](../../doc/models/consumers-balances-401-error.md) |
| 404 | Not found - the server can not find the requested resource. | [`ConsumersBalances404Error`](../../doc/models/consumers-balances-404-error.md) |
| 422 | Unprocessable Entity (WebDAV). If you are receiving an HTTP 422 - Unprocessable Entity error,<br>there are several possibilities for why it might be occurring-<br><br><br>- You are sending in a payload that is not valid JSON. <br><br>- You are sending HTTP headers, such as Content-Type or Accept, which specify a value other than application/json. <br><br>- The request may be valid JSON, but there is something wrong with the content. | [`ConsumersBalances422Error`](../../doc/models/consumers-balances-422-error.md) |
| 429 | Rate limit hit. See the Retry-After header to specify a delay, but note that there is no guarantee that subsequent requests won't be limited. | `ApiError` |
| 500 | Internal error - the server encountered an unexpected condition that prevented it from fulfilling the request. | `ApiError` |

