# Profile Management

```ts
const profileManagementApi = new ProfileManagementApi(client);
```

## Class Name

`ProfileManagementApi`


# Access Code

This endpoint allows get the Access Code from */api/v2/auth/accessCode* endpoint. Use the *accessToken* obtained using */api/v2/auth/exchangeAccessCode* as Bearer in the Authorization header.

:information_source: **Note** This endpoint does not require authentication.

```ts
async accessCode(
  xSsoMarket: string,
  authorization: unknown,
  requestOptions?: RequestOptions
): Promise<ApiResponse<AccessCodeResponse>>
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `xSsoMarket` | `string` | Header, Required | A combination of [language code](https://www.iso.org/standard/22109.html) (lower case) and [country code](https://www.iso.org/iso-3166-country-codes.html) (upper case), separated by a hyphen. For example: **en-TH**. |
| `authorization` | `unknown` | Header, Required | The input value is **Bearer {{accessToken}}**. The value of *accessToken* is retrieved from the */auth/exchangeAccessCode* endpoint. |
| `requestOptions` | `RequestOptions \| undefined` | Optional | Pass additional request options. |

## Response Type

**200**: **OK**. The response includes accessCode and its expiration time of 30 seconds.

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `result` property of this instance returns the response data which is of type [`AccessCodeResponse`](../../doc/models/access-code-response.md).

## Example Usage

```ts
const xSsoMarket = 'en-TH';

const authorization = 'Bearer clna3pz3600ih1vo6pus1w36b';

try {
  const response = await profileManagementApi.accessCode(
    xSsoMarket,
    authorization
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

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| 401 | Unauthorized | `ApiError` |
| 500 | Any unexpected error | [`JsonApiError`](../../doc/models/json-api-error.md) |

