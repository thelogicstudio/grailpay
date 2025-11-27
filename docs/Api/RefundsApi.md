# TheLogicStudio\GrailPay\RefundsApi

API Endpoints used for creating and retrieving refunds.

All URIs are relative to https://api.grailpay.com, except if the operation defines another base path.

| Method | HTTP request | Description |
| ------------- | ------------- | ------------- |
| [**getBatchRefunds()**](RefundsApi.md#getBatchRefunds) | **GET** /3p/api/v2/batch-refunds | Get All Batch Refunds ( STABLE ) |
| [**getTransactionsRefunds()**](RefundsApi.md#getTransactionsRefunds) | **GET** /3p/api/v1/transactions/{transaction_uuid}/refunds | Get Transaction Refunds ( STABLE ) |
| [**postTransactionsRefund()**](RefundsApi.md#postTransactionsRefund) | **POST** /3p/api/v1/transactions/{uuid}/refund | Refund a transaction ( STABLE ) |


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



$apiInstance = new TheLogicStudio\GrailPay\Api\RefundsApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client()
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

No authorization required

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `getTransactionsRefunds()`

```php
getTransactionsRefunds($transaction_uuid): \TheLogicStudio\GrailPay\Model\RefundListResponse
```

Get Transaction Refunds ( STABLE )

This API returns a list of refund requests for a specific transaction.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');



$apiInstance = new TheLogicStudio\GrailPay\Api\RefundsApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client()
);
$transaction_uuid = 9c2af585-9fea-4c47-ac12-e00f42943cd8; // string | Transaction UUID

try {
    $result = $apiInstance->getTransactionsRefunds($transaction_uuid);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling RefundsApi->getTransactionsRefunds: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **transaction_uuid** | **string**| Transaction UUID | |

### Return type

[**\TheLogicStudio\GrailPay\Model\RefundListResponse**](../Model/RefundListResponse.md)

### Authorization

No authorization required

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `postTransactionsRefund()`

```php
postTransactionsRefund($uuid, $v1_refund_transaction_request): \TheLogicStudio\GrailPay\Model\PostTransactionsRefund201Response
```

Refund a transaction ( STABLE )

Once a transaction has been completed, this API can be used to issue a refund, thereby clawing back funds from the payee and transferring them back to the payor. An optional amount can be specified to either issue a partial refund or add additional fees to the original amount. If the amount is not specified, the total transaction amount is refunded.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');



$apiInstance = new TheLogicStudio\GrailPay\Api\RefundsApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client()
);
$uuid = 'uuid_example'; // string | UUID of the transaction to refund
$v1_refund_transaction_request = new \TheLogicStudio\GrailPay\Model\V1RefundTransactionRequest(); // \TheLogicStudio\GrailPay\Model\V1RefundTransactionRequest

try {
    $result = $apiInstance->postTransactionsRefund($uuid, $v1_refund_transaction_request);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling RefundsApi->postTransactionsRefund: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **uuid** | **string**| UUID of the transaction to refund | |
| **v1_refund_transaction_request** | [**\TheLogicStudio\GrailPay\Model\V1RefundTransactionRequest**](../Model/V1RefundTransactionRequest.md)|  | |

### Return type

[**\TheLogicStudio\GrailPay\Model\PostTransactionsRefund201Response**](../Model/PostTransactionsRefund201Response.md)

### Authorization

No authorization required

### HTTP request headers

- **Content-Type**: `application/json`
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)
