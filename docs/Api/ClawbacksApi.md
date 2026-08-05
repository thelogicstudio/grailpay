# TheLogicStudio\GrailPay\ClawbacksApi

Clawbacks

All URIs are relative to https://api.grailpay.com, except if the operation defines another base path.

| Method | HTTP request | Description |
| ------------- | ------------- | ------------- |
| [**getClawbacks()**](ClawbacksApi.md#getClawbacks) | **GET** /api/v3/clawbacks | Get All Clawbacks ( STABLE ) |
| [**getClawbacksByUuid()**](ClawbacksApi.md#getClawbacksByUuid) | **GET** /api/v3/clawbacks/{uuid} | Get Clawback ( STABLE ) |


## `getClawbacks()`

```php
getClawbacks($filter_uuid, $filter_status, $filter_ach_id, $filter_client_reference_id, $filter_start_date, $filter_end_date, $filter_amount, $filter_transaction_uuid, $filter_merchant_uuid, $filter_payee_uuid, $sort, $page, $per_page): \TheLogicStudio\GrailPay\Model\GetClawbacks200Response
```

Get All Clawbacks ( STABLE )

This endpoint provides a paginated list of clawbacks visible to the authenticated user, with filtering and sorting options.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (Token) authorization: ApiToken
$config = TheLogicStudio\GrailPay\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new TheLogicStudio\GrailPay\Api\ClawbacksApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$filter_uuid = 8f5a6e9d-2c41-4f90-bb3f-9e8a9a3b7f1c; // string | Filter by clawback UUID
$filter_status = CLAWBACK_ACH_PENDING; // string | Filter by clawback status
$filter_ach_id = ach_7r9m2f4q8xk1c6v; // string | Filter by clawback ACH trace ID
$filter_client_reference_id = reference_12345; // string | Filter by client reference ID (partial match)
$filter_start_date = Mon Jan 01 13:00:00 NZDT 2024; // \DateTime | Filter clawbacks created on or after this date (YYYY-MM-DD)
$filter_end_date = Tue Dec 31 13:00:00 NZDT 2024; // \DateTime | Filter clawbacks created on or before this date (YYYY-MM-DD)
$filter_amount = >=100; // string | Filter by amount. Supports dynamic operators (e.g. filter[amount]=100, filter[amount]=>100, filter[amount]=<=500)
$filter_transaction_uuid = 4a9f2d71-8e3c-4b65-a1f7-2f6d0c9b8a34; // string | Filter by the parent transaction UUID
$filter_merchant_uuid = 6a8fc154-1a50-483b-a690-fd1dfaf9408b; // string | Filter by merchant UUID on the parent transaction's payee or payer
$filter_payee_uuid = 019e0834-c96a-7cd8-8ef3-70162a383e1f; // string | Filter by payee person or business UUID
$sort = -created_at; // string | Sort by field (created_at, amount). Prefix with '-' for descending order
$page = 1; // int | Page number for pagination
$per_page = 15; // int | Number of records per page

try {
    $result = $apiInstance->getClawbacks($filter_uuid, $filter_status, $filter_ach_id, $filter_client_reference_id, $filter_start_date, $filter_end_date, $filter_amount, $filter_transaction_uuid, $filter_merchant_uuid, $filter_payee_uuid, $sort, $page, $per_page);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling ClawbacksApi->getClawbacks: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **filter_uuid** | **string**| Filter by clawback UUID | [optional] |
| **filter_status** | **string**| Filter by clawback status | [optional] |
| **filter_ach_id** | **string**| Filter by clawback ACH trace ID | [optional] |
| **filter_client_reference_id** | **string**| Filter by client reference ID (partial match) | [optional] |
| **filter_start_date** | **\DateTime**| Filter clawbacks created on or after this date (YYYY-MM-DD) | [optional] |
| **filter_end_date** | **\DateTime**| Filter clawbacks created on or before this date (YYYY-MM-DD) | [optional] |
| **filter_amount** | **string**| Filter by amount. Supports dynamic operators (e.g. filter[amount]&#x3D;100, filter[amount]&#x3D;&gt;100, filter[amount]&#x3D;&lt;&#x3D;500) | [optional] |
| **filter_transaction_uuid** | **string**| Filter by the parent transaction UUID | [optional] |
| **filter_merchant_uuid** | **string**| Filter by merchant UUID on the parent transaction&#39;s payee or payer | [optional] |
| **filter_payee_uuid** | **string**| Filter by payee person or business UUID | [optional] |
| **sort** | **string**| Sort by field (created_at, amount). Prefix with &#39;-&#39; for descending order | [optional] |
| **page** | **int**| Page number for pagination | [optional] |
| **per_page** | **int**| Number of records per page | [optional] [default to 15] |

### Return type

[**\TheLogicStudio\GrailPay\Model\GetClawbacks200Response**](../Model/GetClawbacks200Response.md)

### Authorization

[ApiToken](../../README.md#ApiToken)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `getClawbacksByUuid()`

```php
getClawbacksByUuid($uuid): \TheLogicStudio\GrailPay\Model\GetClawbacksByUuid200Response
```

Get Clawback ( STABLE )

This endpoint returns the details of a single clawback along with identity pointers to its related transaction and payout. The UUID is generated when the clawback is created and is associated with the clawback record.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (Token) authorization: ApiToken
$config = TheLogicStudio\GrailPay\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new TheLogicStudio\GrailPay\Api\ClawbacksApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$uuid = 8f5a6e9d-2c41-4f90-bb3f-9e8a9a3b7f1c; // string | clawback UUID

try {
    $result = $apiInstance->getClawbacksByUuid($uuid);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling ClawbacksApi->getClawbacksByUuid: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **uuid** | **string**| clawback UUID | |

### Return type

[**\TheLogicStudio\GrailPay\Model\GetClawbacksByUuid200Response**](../Model/GetClawbacksByUuid200Response.md)

### Authorization

[ApiToken](../../README.md#ApiToken)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)
