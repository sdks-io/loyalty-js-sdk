# Offer

APIs to assign and revoke an offer for the customer

```ts
const offerApi = new OfferApi(client);
```

## Class Name

`OfferApi`

## Methods

* [Assign Partner Offer](../../doc/controllers/offer.md#assign-partner-offer)
* [Revoke Partner Offer](../../doc/controllers/offer.md#revoke-partner-offer)


# Assign Partner Offer

Assigning a partner based offer to a customer by the partner

```ts
async assignPartnerOffer(
  languageCode: string,
  userAuthorizationToken: string,
  countryCode: string,
  xCorrelationId?: string,
  channel?: AssignOfferChannel,
  application?: string,
  body?: OfferAssignment,
  requestOptions?: RequestOptions
): Promise<ApiResponse<Offer>>
```

## Authentication

This endpoint requires [client-authorization-token](../../doc/auth/oauth-2-client-credentials-grant.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `languageCode` | `string` | Query, Required | This is a concatenation of language in lower case as per ISO 639-1 , “-” and country code as per ISO 3166-1 alpha-2. |
| `userAuthorizationToken` | `string` | Header, Required | The value of the `accessToken` retrieved from the `/auth/exchangeAccessCode` endpoint. This is referred to as user-authorization-token where the access is provided by the end user. |
| `countryCode` | `string` | Header, Required | Two character ISO 3166-1 alpha-2 country code. |
| `xCorrelationId` | `string \| undefined` | Header, Optional | An unique ID in GUID format in order to track the request. |
| `channel` | [`AssignOfferChannel \| undefined`](../../doc/models/assign-offer-channel.md) | Header, Optional | Channel. |
| `application` | `string \| undefined` | Header, Optional | String |
| `body` | [`OfferAssignment \| undefined`](../../doc/models/offer-assignment.md) | Body, Optional | assign offer to customer |
| `requestOptions` | `RequestOptions \| undefined` | Optional | Pass additional request options. |

## Response Type

**200**: Successful partner offer assignment, response contains all relevant data of the Offer.

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `result` property of this instance returns the response data which is of type [`Offer`](../../doc/models/offer.md).

## Example Usage

```ts
const languageCode = 'en-GB';

const userAuthorizationToken = 'ckr08brxj00zp0rqkrlq5526q';

const countryCode = 'GB';

const xCorrelationId = '7c9a45de-00f5-4b13-9a0b-50e16c462a4e';

const channel = AssignOfferChannel.Partner;

const application = 'PARTNER';

const body: OfferAssignment = {
  referenceId: 'as3df5131fas3f54f92h5df',
  consumerUuid: 'cee1157e-cac0-4fc6-b92b-68a13b456b43',
  offerId: 'offerId1234',
  validFrom: '03/08/2021 17:12:55',
  validityPeriod: 31,
  validTo: '03/08/2021 17:12:55',
};

try {
  const response = await offerApi.assignPartnerOffer(
    languageCode,
    userAuthorizationToken,
    countryCode,
    xCorrelationId,
    channel,
    application,
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
    if (error instanceof CommonError) {
      console.log(error.result);
    }
  }
}
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| 400 | Bad request as certain mandatory parameters were not provided by the client in the request. | [`CommonError`](../../doc/models/common-error.md) |
| 401 | Unauthorized request, Missing Authorization header, or expired authorization token. | [`CommonError`](../../doc/models/common-error.md) |
| 404 | Offer/Customer does not exist. | [`CommonError`](../../doc/models/common-error.md) |
| 422 | All offer assignment based error what it caused by the "Offer" | [`CommonError`](../../doc/models/common-error.md) |
| 429 | Rate limit hit. See Retry-After header for a minimum amount of delay, but note that there is no guarantee<br>that subsequent request won't be limited. | `ApiError` |
| 500 | Internal server error | `ApiError` |


# Revoke Partner Offer

Revoking a partner based offer from customer by Partner.

```ts
async revokePartnerOffer(
  languageCode: string,
  userAuthorizationToken: string,
  clientAuthorizationToken: string,
  countryCode: string,
  consumerUuid: string,
  partnerReferenceId: string,
  xCorrelationId?: string,
  channel?: AssignOfferChannel,
  application?: string,
  requestOptions?: RequestOptions
): Promise<ApiResponse<Offer>>
```

## Authentication

This endpoint requires [client-authorization-token](../../doc/auth/oauth-2-client-credentials-grant.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `languageCode` | `string` | Query, Required | This is a concatenation of language in lower case as per ISO 639-1 , “-” and country code as per ISO 3166-1 alpha-2. |
| `userAuthorizationToken` | `string` | Header, Required | The value of the `accessToken` retrieved from the `/auth/exchangeAccessCode` endpoint. This is referred to as user-authorization-token where the access is provided by the end user. |
| `clientAuthorizationToken` | `string` | Header, Required | The value of the `accessToken` retrieved from the `/oauth/token` endpoint. This is client authorization between Shell and Partner system. |
| `countryCode` | `string` | Header, Required | Two character ISO 3166-1 alpha-2 country code. |
| `consumerUuid` | `string` | Header, Required | SSO uuid of the user signed in with Shell credentials. |
| `partnerReferenceId` | `string` | Header, Required | Unique Reference ID for the transaction which was used when assigning the offer from the partner in Assign Offer API |
| `xCorrelationId` | `string \| undefined` | Header, Optional | An unique ID in GUID format in order to track the request. |
| `channel` | [`AssignOfferChannel \| undefined`](../../doc/models/assign-offer-channel.md) | Header, Optional | Channel. |
| `application` | `string \| undefined` | Header, Optional | String |
| `requestOptions` | `RequestOptions \| undefined` | Optional | Pass additional request options. |

## Response Type

**200**: Successful partner offer assignment, response contains all relevant data of the Offer.

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `result` property of this instance returns the response data which is of type [`Offer`](../../doc/models/offer.md).

## Example Usage

```ts
const languageCode = 'en-GB';

const userAuthorizationToken = 'ckr08brxj00zp0rqkrlq5526q';

const clientAuthorizationToken = 'dtcdhdhTGSAHSJS78HAJAN';

const countryCode = 'GB';

const consumerUuid = '7c9a45de-00f5-4b13-9a0b-50e16c462a4e';

const partnerReferenceId = '7c9a45de-00f5-4b13-9a0b-50e16c462a4e';

const xCorrelationId = '7c9a45de-00f5-4b13-9a0b-50e16c462a4e';

const channel = AssignOfferChannel.Partner;

const application = 'PARTNER';

try {
  const response = await offerApi.revokePartnerOffer(
    languageCode,
    userAuthorizationToken,
    clientAuthorizationToken,
    countryCode,
    consumerUuid,
    partnerReferenceId,
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
    if (error instanceof CommonError) {
      console.log(error.result);
    }
  }
}
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| 400 | Bad request as certain mandatory parameters were not provided by the client in the request. | [`CommonError`](../../doc/models/common-error.md) |
| 401 | Unauthorized request, Missing Authorization header, or expired authorization token. | [`CommonError`](../../doc/models/common-error.md) |
| 404 | Offer/Customer does not exist. | [`CommonError`](../../doc/models/common-error.md) |
| 422 | All offer assignment based error what it caused by the "Offer" | [`CommonError`](../../doc/models/common-error.md) |
| 429 | Rate limit hit. See Retry-After header for a minimum amount of delay, but note that there is no guarantee<br>that subsequent request won't be limited. | `ApiError` |
| 500 | Internal server error | `ApiError` |

