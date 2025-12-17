# TheLogicStudio\GrailPay\RefundsApi

API Endpoints used for creating and retrieving refunds.

All URIs are relative to https://api.grailpay.com, except if the operation defines another base path.

| Method | HTTP request | Description |
| ------------- | ------------- | ------------- |
| [**getBatchRefunds()**](RefundsApi.md#getBatchRefunds) | **GET** /3p/api/v2/batch-refunds | Get All Batch Refunds ( STABLE ) |
| [**getBatchRefundsByBatchRefundUuid()**](RefundsApi.md#getBatchRefundsByBatchRefundUuid) | **GET** /3p/api/v2/batch-refunds/{batch_refund_uuid} | Get Batch Refund ( STABLE ) |
| [**getRefundsByRefundUuid()**](RefundsApi.md#getRefundsByRefundUuid) | **GET** /3p/api/v1/refunds/{refund_uuid} | Get Refund Details ( Refunds ) |
| [**getTransactionsByTransactionUuidRefunds()**](RefundsApi.md#getTransactionsByTransactionUuidRefunds) | **GET** /3p/api/v1/transactions/{transaction_uuid}/refunds | Get Transaction Refunds ( STABLE ) |
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


// Configure Bearer (Token) authorization: APIToken
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

[APIToken](../../README.md#APIToken)

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


// Configure Bearer (Token) authorization: APIToken
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

[APIToken](../../README.md#APIToken)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `getRefundsByRefundUuid()`

```php
getRefundsByRefundUuid($refund_uuid): \TheLogicStudio\GrailPay\Model\GetRefundsByRefundUuid200Response
```

Get Refund Details ( Refunds )

This API returns the details of a refund request.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (Token) authorization: APIToken
$config = TheLogicStudio\GrailPay\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new TheLogicStudio\GrailPay\Api\RefundsApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$refund_uuid = 'refund_uuid_example'; // string | Refund UUID

try {
    $result = $apiInstance->getRefundsByRefundUuid($refund_uuid);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling RefundsApi->getRefundsByRefundUuid: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **refund_uuid** | **string**| Refund UUID | |

### Return type

[**\TheLogicStudio\GrailPay\Model\GetRefundsByRefundUuid200Response**](../Model/GetRefundsByRefundUuid200Response.md)

### Authorization

[APIToken](../../README.md#APIToken)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `getTransactionsByTransactionUuidRefunds()`

```php
getTransactionsByTransactionUuidRefunds($transaction_uuid): \TheLogicStudio\GrailPay\Model\RefundListResponse
```

Get Transaction Refunds ( STABLE )

This API returns a list of refund requests for a specific transaction.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (Token) authorization: APIToken
$config = TheLogicStudio\GrailPay\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new TheLogicStudio\GrailPay\Api\RefundsApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$transaction_uuid = 9c2af585-9fea-4c47-ac12-e00f42943cd8; // string | Transaction UUID

try {
    $result = $apiInstance->getTransactionsByTransactionUuidRefunds($transaction_uuid);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling RefundsApi->getTransactionsByTransactionUuidRefunds: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **transaction_uuid** | **string**| Transaction UUID | |

### Return type

[**\TheLogicStudio\GrailPay\Model\RefundListResponse**](../Model/RefundListResponse.md)

### Authorization

[APIToken](../../README.md#APIToken)

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


// Configure Bearer (Token) authorization: APIToken
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

[APIToken](../../README.md#APIToken)

### HTTP request headers

- **Content-Type**: `application/json`
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)
