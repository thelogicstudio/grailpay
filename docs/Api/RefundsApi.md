# TheLogicStudio\GrailPay\RefundsApi

API Endpoints used for creating and retrieving refunds.

All URIs are relative to https://api.grailpay.com, except if the operation defines another base path.

| Method | HTTP request | Description |
| ------------- | ------------- | ------------- |
| [**getBatchRefunds()**](RefundsApi.md#getBatchRefunds) | **GET** /3p/api/v2/batch-refunds | Get All Batch Refunds ( STABLE ) |
| [**getBatchRefundsByBatchRefundUuid()**](RefundsApi.md#getBatchRefundsByBatchRefundUuid) | **GET** /3p/api/v2/batch-refunds/{batch_refund_uuid} | Get Batch Refund ( STABLE ) |
| [**getRefunds()**](RefundsApi.md#getRefunds) | **GET** /api/v3/refunds | Get All Refunds ( STABLE ) |
| [**getRefundsByUuid()**](RefundsApi.md#getRefundsByUuid) | **GET** /api/v3/refunds/{uuid} | Get Refund ( STABLE ) |
| [**postTransactionsByUuidRefund()**](RefundsApi.md#postTransactionsByUuidRefund) | **POST** /3p/api/v1/transactions/{uuid}/refund | Refund a transaction ( STABLE ) |


## `getBatchRefunds()`

```php
getBatchRefunds($start_date, $end_date, $sort_order, $page, $per_page): \TheLogicStudio\GrailPay\Model\BatchRefundListResponse
```

Get All Batch Refunds ( STABLE )

This API retrieves a list of all batch refunds. The response provides details for each batch refund, including the total amount and relevant timestamps. Pagination options are available to efficiently manage large datasets.

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
$start_date = Fri Mar 01 13:00:00 NZDT 2024; // \DateTime | This parameter will filter the user's records based on the creation date of the batch refund.Date format: Y-m-d
$end_date = Sun Mar 10 13:00:00 NZDT 2024; // \DateTime | This parameter will filter the user's records based on the creation date of the batch refund.Date format: Y-m-d
$sort_order = newest; // string | Sorting order: 'oldest' for ascending, 'newest' for descending.
$page = 1; // int | Page number for pagination.
$per_page = 10; // int | Number of items per page.

try {
    $result = $apiInstance->getBatchRefunds($start_date, $end_date, $sort_order, $page, $per_page);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling RefundsApi->getBatchRefunds: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **start_date** | **\DateTime**| This parameter will filter the user&#39;s records based on the creation date of the batch refund.Date format: Y-m-d | [optional] |
| **end_date** | **\DateTime**| This parameter will filter the user&#39;s records based on the creation date of the batch refund.Date format: Y-m-d | [optional] |
| **sort_order** | **string**| Sorting order: &#39;oldest&#39; for ascending, &#39;newest&#39; for descending. | [optional] |
| **page** | **int**| Page number for pagination. | [optional] |
| **per_page** | **int**| Number of items per page. | [optional] |

### Return type

[**\TheLogicStudio\GrailPay\Model\BatchRefundListResponse**](../Model/BatchRefundListResponse.md)

### Authorization

[ApiToken](../../README.md#ApiToken)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `getBatchRefundsByBatchRefundUuid()`

```php
getBatchRefundsByBatchRefundUuid($batch_refund_uuid): \TheLogicStudio\GrailPay\Model\GetBatchRefundsByBatchRefundUuid200Response
```

Get Batch Refund ( STABLE )

This API retrieves the details of a specific batch refund using its unique batch refund UUID. The response provides comprehensive information about the refund, including the total amount and the associated transactions.

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
$batch_refund_uuid = 'batch_refund_uuid_example'; // string | UUID of the batch refund

try {
    $result = $apiInstance->getBatchRefundsByBatchRefundUuid($batch_refund_uuid);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling RefundsApi->getBatchRefundsByBatchRefundUuid: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **batch_refund_uuid** | **string**| UUID of the batch refund | |

### Return type

[**\TheLogicStudio\GrailPay\Model\GetBatchRefundsByBatchRefundUuid200Response**](../Model/GetBatchRefundsByBatchRefundUuid200Response.md)

### Authorization

[ApiToken](../../README.md#ApiToken)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `getRefunds()`

```php
getRefunds($filter_uuid, $filter_status, $filter_ach_id, $filter_r_code, $filter_start_date, $filter_end_date, $filter_amount, $filter_transaction_uuid, $filter_merchant_uuid, $sort, $page, $per_page): \TheLogicStudio\GrailPay\Model\GetRefunds200Response
```

Get All Refunds ( STABLE )

This endpoint provides a paginated list of refunds visible to the authenticated user, with filtering and sorting options.

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
$filter_status = REFUND_COMPLETE; // string | Filter by refund status
$filter_ach_id = ach_1331Ds7MrGmp8iCkEFFdmR; // string | Filter by capture or refund ACH trace ID
$filter_r_code = R01; // string | Filter by ACH return code
$filter_start_date = Mon Jan 01 13:00:00 NZDT 2024; // \DateTime | Filter refunds created on or after this date (YYYY-MM-DD)
$filter_end_date = Tue Dec 31 13:00:00 NZDT 2024; // \DateTime | Filter refunds created on or before this date (YYYY-MM-DD)
$filter_amount = >=100; // string | Filter by amount. Supports dynamic operators (e.g. filter[amount]=100, filter[amount]=>100, filter[amount]=<=500)
$filter_transaction_uuid = 3fa85f64-5717-4562-b3fc-2c963f66afa6; // string | Filter by the parent transaction UUID
$filter_merchant_uuid = 6a8fc154-1a50-483b-a690-fd1dfaf9408b; // string | Filter by payee or payer merchant UUID
$sort = -created_at; // string | Sort by field (created_at, amount). Prefix with '-' for descending order
$page = 1; // int | Page number for pagination
$per_page = 15; // int | Number of records per page

try {
    $result = $apiInstance->getRefunds($filter_uuid, $filter_status, $filter_ach_id, $filter_r_code, $filter_start_date, $filter_end_date, $filter_amount, $filter_transaction_uuid, $filter_merchant_uuid, $sort, $page, $per_page);
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

Get Refund ( STABLE )

This endpoint returns the details of a single refund along with its parent transaction. The UUID is generated when the refund is created and is associated with the refund record.

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

## `postTransactionsByUuidRefund()`

```php
postTransactionsByUuidRefund($uuid, $v1_refund_transaction_request): \TheLogicStudio\GrailPay\Model\PostTransactionsByUuidRefund201Response
```

Refund a transaction ( STABLE )

Once a transaction has been completed, this API can be used to issue a refund, thereby clawing back funds from the payee and transferring them back to the payor. An optional amount can be specified to either issue a partial refund or add additional fees to the original amount. If the amount is not specified, the total transaction amount is refunded.

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
$uuid = 'uuid_example'; // string | UUID of the transaction to refund
$v1_refund_transaction_request = new \TheLogicStudio\GrailPay\Model\V1RefundTransactionRequest(); // \TheLogicStudio\GrailPay\Model\V1RefundTransactionRequest

try {
    $result = $apiInstance->postTransactionsByUuidRefund($uuid, $v1_refund_transaction_request);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling RefundsApi->postTransactionsByUuidRefund: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **uuid** | **string**| UUID of the transaction to refund | |
| **v1_refund_transaction_request** | [**\TheLogicStudio\GrailPay\Model\V1RefundTransactionRequest**](../Model/V1RefundTransactionRequest.md)|  | |

### Return type

[**\TheLogicStudio\GrailPay\Model\PostTransactionsByUuidRefund201Response**](../Model/PostTransactionsByUuidRefund201Response.md)

### Authorization

[ApiToken](../../README.md#ApiToken)

### HTTP request headers

- **Content-Type**: `application/json`
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)
