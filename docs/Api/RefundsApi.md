# TheLogicStudio\GrailPay\RefundsApi

API Endpoints used for creating and retrieving refunds.

All URIs are relative to https://api.grailpay.com, except if the operation defines another base path.

| Method | HTTP request | Description |
| ------------- | ------------- | ------------- |
| [**getRefunds()**](RefundsApi.md#getRefunds) | **GET** /api/v3/refunds | Get All Refunds |
| [**getRefundsByUuid()**](RefundsApi.md#getRefundsByUuid) | **GET** /api/v3/refunds/{uuid} | Get Refund |
| [**postRefunds()**](RefundsApi.md#postRefunds) | **POST** /api/v3/refunds | Create Refund |


## `getRefunds()`

```php
getRefunds($filter_uuid, $filter_status, $filter_ach_id, $filter_r_code, $filter_start_date, $filter_end_date, $filter_amount, $filter_transaction_uuid, $filter_merchant_uuid, $filter_batch_uuid, $filter_is_batch, $sort, $page, $per_page): \TheLogicStudio\GrailPay\Model\GetRefunds200Response
```

Get All Refunds

This endpoint provides a paginated list of refunds visible to the authenticated user, with filtering and sorting options. Each refund includes batch membership fields (`is_batch`, `batch_uuid`, and an optional `batch` summary). Newly created refunds may appear with status `QUEUED` until origination capacity is available.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (Token) authorization: ApiToken
$config = TheLogicStudio\GrailPay\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new TheLogicStudio\GrailPay\Api\RefundsApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$filter_uuid = 7c41f6a2-a4b9-4df8-9225-2c1b7312042e; // string | Filter by refund UUID
$filter_status = QUEUED; // string | Filter by refund status
$filter_ach_id = ach_1331Ds7MrGmp8iCkEFFdmR; // string | Filter by capture or refund ACH trace ID
$filter_r_code = R01; // string | Filter by ACH return code
$filter_start_date = Mon Jan 01 13:00:00 NZDT 2024; // \DateTime | Filter refunds created on or after this date (YYYY-MM-DD)
$filter_end_date = Tue Dec 31 13:00:00 NZDT 2024; // \DateTime | Filter refunds created on or before this date (YYYY-MM-DD)
$filter_amount = >=100; // string | Filter by amount. Supports dynamic operators (e.g. filter[amount]=100, filter[amount]=>100, filter[amount]=<=500)
$filter_transaction_uuid = 3fa85f64-5717-4562-b3fc-2c963f66afa6; // string | Filter by the parent transaction UUID
$filter_merchant_uuid = 6a8fc154-1a50-483b-a690-fd1dfaf9408b; // string | Filter by payee or payer merchant UUID
$filter_batch_uuid = 3fa85f64-5717-4562-b3fc-2c963f66afa6; // string | Filter by batch UUID
$filter_is_batch = true; // string | Filter by batch membership (true/false/1/0)
$sort = -created_at; // string | Sort by field (created_at, amount). Prefix with '-' for descending order
$page = 1; // int | Page number for pagination
$per_page = 15; // int | Number of records per page

try {
    $result = $apiInstance->getRefunds($filter_uuid, $filter_status, $filter_ach_id, $filter_r_code, $filter_start_date, $filter_end_date, $filter_amount, $filter_transaction_uuid, $filter_merchant_uuid, $filter_batch_uuid, $filter_is_batch, $sort, $page, $per_page);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling RefundsApi->getRefunds: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **filter_uuid** | **string**| Filter by refund UUID | [optional] |
| **filter_status** | **string**| Filter by refund status | [optional] |
| **filter_ach_id** | **string**| Filter by capture or refund ACH trace ID | [optional] |
| **filter_r_code** | **string**| Filter by ACH return code | [optional] |
| **filter_start_date** | **\DateTime**| Filter refunds created on or after this date (YYYY-MM-DD) | [optional] |
| **filter_end_date** | **\DateTime**| Filter refunds created on or before this date (YYYY-MM-DD) | [optional] |
| **filter_amount** | **string**| Filter by amount. Supports dynamic operators (e.g. filter[amount]&#x3D;100, filter[amount]&#x3D;&gt;100, filter[amount]&#x3D;&lt;&#x3D;500) | [optional] |
| **filter_transaction_uuid** | **string**| Filter by the parent transaction UUID | [optional] |
| **filter_merchant_uuid** | **string**| Filter by payee or payer merchant UUID | [optional] |
| **filter_batch_uuid** | **string**| Filter by batch UUID | [optional] |
| **filter_is_batch** | **string**| Filter by batch membership (true/false/1/0) | [optional] |
| **sort** | **string**| Sort by field (created_at, amount). Prefix with &#39;-&#39; for descending order | [optional] |
| **page** | **int**| Page number for pagination | [optional] |
| **per_page** | **int**| Number of records per page | [optional] [default to 15] |

### Return type

[**\TheLogicStudio\GrailPay\Model\GetRefunds200Response**](../Model/GetRefunds200Response.md)

### Authorization

[ApiToken](../../README.md#ApiToken)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `getRefundsByUuid()`

```php
getRefundsByUuid($uuid): \TheLogicStudio\GrailPay\Model\GetRefundsByUuid200Response
```

Get Refund

This endpoint returns the details of a single refund along with its parent transaction. The response uses the same refund representation as the list endpoint, including batch membership fields (`is_batch`, `batch_uuid`, and an optional `batch` summary).

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (Token) authorization: ApiToken
$config = TheLogicStudio\GrailPay\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new TheLogicStudio\GrailPay\Api\RefundsApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$uuid = 7c41f6a2-a4b9-4df8-9225-2c1b7312042e; // string | refund UUID

try {
    $result = $apiInstance->getRefundsByUuid($uuid);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling RefundsApi->getRefundsByUuid: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **uuid** | **string**| refund UUID | |

### Return type

[**\TheLogicStudio\GrailPay\Model\GetRefundsByUuid200Response**](../Model/GetRefundsByUuid200Response.md)

### Authorization

[ApiToken](../../README.md#ApiToken)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `postRefunds()`

```php
postRefunds($post_refunds_request, $idempotency_key): \TheLogicStudio\GrailPay\Model\PostRefunds201Response
```

Create Refund

Creates a refund against a completed payout transaction. The refund is persisted immediately and typically returned with status `QUEUED` until ACH origination capacity is available. Supports idempotency via the `Idempotency-Key` header. Newly created refunds are not batched (`is_batch` is false and `batch` is null) until later processing assigns a batch.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (Token) authorization: ApiToken
$config = TheLogicStudio\GrailPay\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new TheLogicStudio\GrailPay\Api\RefundsApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$post_refunds_request = new \TheLogicStudio\GrailPay\Model\PostRefundsRequest(); // \TheLogicStudio\GrailPay\Model\PostRefundsRequest | Refund creation payload. Amount is in cents.
$idempotency_key = refund-idempotency-key-123; // string | Optional idempotency key. Replaying the same key with the same request body returns the original response; a conflicting body returns 409.

try {
    $result = $apiInstance->postRefunds($post_refunds_request, $idempotency_key);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling RefundsApi->postRefunds: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **post_refunds_request** | [**\TheLogicStudio\GrailPay\Model\PostRefundsRequest**](../Model/PostRefundsRequest.md)| Refund creation payload. Amount is in cents. | |
| **idempotency_key** | **string**| Optional idempotency key. Replaying the same key with the same request body returns the original response; a conflicting body returns 409. | [optional] |

### Return type

[**\TheLogicStudio\GrailPay\Model\PostRefunds201Response**](../Model/PostRefunds201Response.md)

### Authorization

[ApiToken](../../README.md#ApiToken)

### HTTP request headers

- **Content-Type**: `application/json`
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)
