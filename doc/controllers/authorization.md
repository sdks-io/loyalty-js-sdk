# Authorization

Token and access code management

```ts
const authorizationApi = new AuthorizationApi(client);
```

## Class Name

`AuthorizationApi`

## Methods

* [Get Authorization Token](../../doc/controllers/authorization.md#get-authorization-token)
* [Exchange Access Code](../../doc/controllers/authorization.md#exchange-access-code)
* [Refresh](../../doc/controllers/authorization.md#refresh)


# Get Authorization Token

When partner wants to get the basic public token, to be authorized to perform any other call inside SSO, needs to call this endpoint

:information_source: **Note** This endpoint does not require authentication.

```ts
async getAuthorizationToken(
  body: AuthTokenRequest,
  requestOptions?: RequestOptions
): Promise<ApiResponse<AuthTokenResponse>>
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `body` | [`AuthTokenRequest`](../../doc/models/auth-token-request.md) | Body, Required | Digest data generated using sha256(client_id) |
| `requestOptions` | `RequestOptions \| undefined` | Optional | Pass additional request options. |

## Response Type

**200**: OK

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `result` property of this instance returns the response data which is of type [`AuthTokenResponse`](../../doc/models/auth-token-response.md).

## Example Usage

```ts
const body: AuthTokenRequest = {
  digest: 'Aaaaaaaaaaaaaa',
};

try {
  const response = await authorizationApi.getAuthorizationToken(body);

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
    if (error instanceof JsonApiError) {
      console.log(error.result);
    }
  }
}
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| 400 | Bad Request. If the request is missing the digest field | [`JsonApiError`](../../doc/models/json-api-error.md) |
| 401 | Unauthorized. If the digest provided is not valid | [`JsonApiError`](../../doc/models/json-api-error.md) |
| 500 | Any unexpected error | [`JsonApiError`](../../doc/models/json-api-error.md) |


# Exchange Access Code

This endpoint allows to given an access code to retrieve an user profile with a pair of valid tokens. In this end point, accessCode can be exchanged for an accessToken which is user-authorization-token.

```ts
async exchangeAccessCode(
  authorization: string,
  body: ExchangeAccessCodeRequest,
  requestOptions?: RequestOptions
): Promise<ApiResponse<M200UserPartners>>
```

## Authentication

This endpoint requires [PublicBasicToken](../../doc/auth/custom-header-signature.md)

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `authorization` | `string` | Header, Required | Basic Public token which was generated with auth/token end point. |
| `body` | [`ExchangeAccessCodeRequest`](../../doc/models/exchange-access-code-request.md) | Body, Required | Exchange access code data |
| `requestOptions` | `RequestOptions \| undefined` | Optional | Pass additional request options. |

## Response Type

**200**: The response include the SSO user profile and a pair of access token and refresh token

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `result` property of this instance returns the response data which is of type [`M200UserPartners`](../../doc/models/m200-user-partners.md).

## Example Usage

```ts
const authorization = 'Basic 31d9027a8...42146af077';

const body: ExchangeAccessCodeRequest = {
  accessCode: 'AAAAAAAAAAAAA',
};

try {
  const response = await authorizationApi.exchangeAccessCode(
    authorization,
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
    if (error instanceof JsonApiError) {
      console.log(error.result);
    }
  }
}
```

## Example Response *(as JSON)*

```json
{
  "uuid": "bb0dffbe‑95c8‑442f‑b15e‑53b8cf0a3d99",
  "userStatus": "UNVERIFIED",
  "market": {
    "code": "en‑GB",
    "country": "GB"
  },
  "accessToken": "ACCESS_TOKEN",
  "refreshToken": "REFRESH_TOKEN"
}
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| 401 | Unauthorized. If making the call with an invalid token | [`JsonApiError`](../../doc/models/json-api-error.md) |
| 404 | Not found. If the access code is not in the database | [`JsonApiError`](../../doc/models/json-api-error.md) |
| 500 | Any unexpected error | [`JsonApiError`](../../doc/models/json-api-error.md) |


# Refresh

When an access token has expired, a partner that wants to get a new pair of valid tokens to go on performing operations against SSO needs to call this endpoint.

:information_source: **Note** This endpoint does not require authentication.

```ts
async refresh(
  authorization: string,
  body?: RefreshTokenRequest,
  requestOptions?: RequestOptions
): Promise<ApiResponse<RefreshTokenResponse>>
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `authorization` | `string` | Header, Required | Basic Public token which was generated with auth/token end point. |
| `body` | [`RefreshTokenRequest \| undefined`](../../doc/models/refresh-token-request.md) | Body, Optional | - |
| `requestOptions` | `RequestOptions \| undefined` | Optional | Pass additional request options. |

## Response Type

**200**: OK. Access token and refresh token are returned.

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `result` property of this instance returns the response data which is of type [`RefreshTokenResponse`](../../doc/models/refresh-token-response.md).

## Example Usage

```ts
const authorization = 'Basic 31d9027a8...42146af077';

const body: RefreshTokenRequest = {
  refreshToken: 'x5as2qv8hpercvq867gu',
};

try {
  const response = await authorizationApi.refresh(
    authorization,
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
    if (error instanceof JsonApiError) {
      console.log(error.result);
    }
  }
}
```

## Example Response *(as JSON)*

```json
{
  "accessToken": "bzrz5f3qegav7xqv",
  "refreshToken": "u6junnmqqmsxx27ynsba",
  "expiresIn": 3600
}
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| 400 | Bad Request. The request is missing the Refresh Token field. | [`JsonApiError`](../../doc/models/json-api-error.md) |
| 401 | Unauthorized. This response is generated when either the Basic Token is invalid or the Refresh Token is invalid (see examples) | [`JsonApiError`](../../doc/models/json-api-error.md) |
| 500 | Any unexpected error | [`JsonApiError`](../../doc/models/json-api-error.md) |

