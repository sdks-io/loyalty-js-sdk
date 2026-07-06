# Redemption

API for customer to redeem loyalty points

```ts
const redemptionApi = new RedemptionApi(client);
```

## Class Name

`RedemptionApi`


# Point Redemption

Point redemption API for customers to redeem loyalty points via the partner channel

```ts
async pointRedemption(
  languageCode: string,
  userAuthorizationToken: string,
  consumerUuid: string,
  countryCode: string,
  xCorrelationId?: string,
  channel?: AssignOfferChannel,
  application?: string,
  retryAfter?: number,
  body?: RedemptionRequest,
  requestOptions?: RequestOptions
): Promise<ApiResponse<RedemptionResponse>>
```

## Authentication

This endpoint requires [client-authorization-token](../../doc/auth/oauth-2-client-credentials-grant.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `languageCode` | `string` | Query, Required | A combination of [language code](https://www.iso.org/standard/22109.html) (lower case) and [country code](https://www.iso.org/iso-3166-country-codes.html) (upper case), separated by a hyphen. |
| `userAuthorizationToken` | `string` | Header, Required | The value of the accessToken retrieved from the /auth/exchangeAccessCode endpoint. This is referred to as user-authorization-token where the access is provided by the end user. |
| `consumerUuid` | `string` | Header, Required | SSO uuid of the user signed in with Shell credentials Format: 32 hexadecimal digits grouped the following way: xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx |
| `countryCode` | `string` | Header, Required | The two character ISO 3166-1 alpha-2 [country code](https://www.iso.org/iso-3166-country-codes.html). |
| `xCorrelationId` | `string \| undefined` | Header, Optional | An unique ID in GUID format in order to track the request. |
| `channel` | [`AssignOfferChannel \| undefined`](../../doc/models/assign-offer-channel.md) | Header, Optional | Channel. |
| `application` | `string \| undefined` | Header, Optional | String |
| `retryAfter` | `number \| undefined` | Header, Optional | Retry the operation after a specified number of seconds have elapsed. |
| `body` | [`RedemptionRequest \| undefined`](../../doc/models/redemption-request.md) | Body, Optional | Redeem a customer's loyalty points |
| `requestOptions` | `RequestOptions \| undefined` | Optional | Pass additional request options. |

## Response Type

**200**: This API is used for Point Redemption by Customer and Partner

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `result` property of this instance returns the response data which is of type [`RedemptionResponse`](../../doc/models/redemption-response.md).

## Example Usage

```ts
const languageCode = 'en-GB';

const userAuthorizationToken = 'Bearer asdfhalsdfheywuiryafhk';

const consumerUuid = 'cee1157e-cac0-4fc6-b92b-68a13b456b43';

const countryCode = 'GB';

const xCorrelationId = '8483a8c3-e2c7-4849-835f-8ed27e5be276';

const channel = AssignOfferChannel.Partner;

const application = 'PARTNER';

const retryAfter = 5;

const body: RedemptionRequest = {
  uuid: 'cee1157e-cac0-4fc6-b92b-68a13b456b43',
  referenceId: 'as3df5131fas3f54f92h5df',
  redemptionReqArray: [
    {
      itemId: '1005',
      points: 50,
      reasonForRedemption: 'Cheeseburger',
      quantity: 2,
    },
    {
      itemId: '1006',
      points: 20,
      reasonForRedemption: 'Chips',
      quantity: 1,
    },
    {
      itemId: '1007',
      points: 10,
      reasonForRedemption: 'Ice Cream',
    }
  ],
};

try {
  const response = await redemptionApi.pointRedemption(
    languageCode,
    userAuthorizationToken,
    consumerUuid,
    countryCode,
    xCorrelationId,
    channel,
    application,
    retryAfter,
    body
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
    }
  }
}
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| 400 | Bad request - The request was not valid. This code is returned when the server has attempted to process the request, but some aspect of the request is not valid, for example an incorrectly formatted resource or an attempt to deploy an invalid event project to the event runtime. Information about the request is provided in the response body, and includes an error code and error message. | [`ConsumersBalances400Error`](../../doc/models/consumers-balances-400-error.md) |
| 401 | Unauthorized request, Missing Authorization header, or expired authorization token etc. It is returned from the application server<br>when application security is enabled, and authorization information was missing from the request. | [`ConsumersBalances400Error`](../../doc/models/consumers-balances-400-error.md) |
| 404 | Not found - the server can not find the requested resource. | [`ConsumersBalances400Error`](../../doc/models/consumers-balances-400-error.md) |
| 422 | Unprocessable Entity (WebDAV). If you are receiving an HTTP 422 - Unprocessable Entity error,<br>there are several possibilities for why it might be occurring-<br><br><br>- You are sending in a payload that is not valid JSON. <br><br>- You are sending HTTP headers, such as Content-Type or Accept, which specify a value other than application/json. <br><br>- The request may be valid JSON, but there is something wrong with the content. | [`ConsumersBalances400Error`](../../doc/models/consumers-balances-400-error.md) |
| 429 | Rate limit hit. See the Retry-After header to specify a delay, but note that there is no guarantee that subsequent requests won't be limited. | `ApiError` |
| 500 | Internal server error | `ApiError` |

