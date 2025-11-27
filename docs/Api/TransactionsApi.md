# TheLogicStudio\GrailPay\TransactionsApi

API Endpoints used for creating and managing transactions.

All URIs are relative to https://api.grailpay.com, except if the operation defines another base path.

| Method | HTTP request | Description |
| ------------- | ------------- | ------------- |
| [**deleteTransactions()**](TransactionsApi.md#deleteTransactions) | **DELETE** /3p/api/v2/transactions/{uuid} | Cancel a transaction ( STABLE ) |
| [**getTransactions()**](TransactionsApi.md#getTransactions) | **GET** /3p/api/v2/transactions | Get Transactions ( STABLE ) |
| [**postTransaction()**](TransactionsApi.md#postTransaction) | **POST** /3p/api/v1/transaction | Create a new transaction ( STABLE ) |


## `deleteTransactions()`

```php
deleteTransactions($uuid): \TheLogicStudio\GrailPay\Model\DeleteTransactions204Response
```

Cancel a transaction ( STABLE )

A transaction can only be canceled while in the CAPTURE_PENDING state. You can no longer cancel a transaction after the ACH capture process has begun.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');



$apiInstance = new TheLogicStudio\GrailPay\Api\TransactionsApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client()
);
$uuid = 'uuid_example'; // string | UUID of the transaction to cancel

try {
    $result = $apiInstance->deleteTransactions($uuid);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling TransactionsApi->deleteTransactions: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **uuid** | **string**| UUID of the transaction to cancel | |

### Return type

[**\TheLogicStudio\GrailPay\Model\DeleteTransactions204Response**](../Model/DeleteTransactions204Response.md)

### Authorization

No authorization required

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `getTransactions()`

```php
getTransactions($per_page, $page, $start_date, $end_date, $sort_order, $payer_account_uuid, $payer_account_aggregator_type, $payee_account_uuid, $payee_account_aggregator_type): \TheLogicStudio\GrailPay\Model\GetTransactions200Response
```

Get Transactions ( STABLE )

Retrieve a list of transactions based on filter parameters

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');



$apiInstance = new TheLogicStudio\GrailPay\Api\TransactionsApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client()
);
$per_page = 56; // int | Number of records per page
$page = 56; // int | Page number
$start_date = new \DateTime('2013-10-20T19:20:30+01:00'); // \DateTime | Start date for filtering transactions
$end_date = new \DateTime('2013-10-20T19:20:30+01:00'); // \DateTime | End date for filtering transactions
$sort_order = 'sort_order_example'; // string | Sort order
$payer_account_uuid = 'payer_account_uuid_example'; // string | UUID of the payer account
$payer_account_aggregator_type = 'payer_account_aggregator_type_example'; // string | Aggregator type of the payer account (Required when payer_account_uuid is provided)
$payee_account_uuid = 'payee_account_uuid_example'; // string | UUID of the payee account
$payee_account_aggregator_type = 'payee_account_aggregator_type_example'; // string | Aggregator type of the payee account

try {
    $result = $apiInstance->getTransactions($per_page, $page, $start_date, $end_date, $sort_order, $payer_account_uuid, $payer_account_aggregator_type, $payee_account_uuid, $payee_account_aggregator_type);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling TransactionsApi->getTransactions: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **per_page** | **int**| Number of records per page | [optional] |
| **page** | **int**| Page number | [optional] |
| **start_date** | **\DateTime**| Start date for filtering transactions | [optional] |
| **end_date** | **\DateTime**| End date for filtering transactions | [optional] |
| **sort_order** | **string**| Sort order | [optional] |
| **payer_account_uuid** | **string**| UUID of the payer account | [optional] |
| **payer_account_aggregator_type** | **string**| Aggregator type of the payer account (Required when payer_account_uuid is provided) | [optional] |
| **payee_account_uuid** | **string**| UUID of the payee account | [optional] |
| **payee_account_aggregator_type** | **string**| Aggregator type of the payee account | [optional] |

### Return type

[**\TheLogicStudio\GrailPay\Model\GetTransactions200Response**](../Model/GetTransactions200Response.md)

### Authorization

No authorization required

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `postTransaction()`

```php
postTransaction($create_transaction): \TheLogicStudio\GrailPay\Model\PostTransaction201Response
```

Create a new transaction ( STABLE )

Once authenticated, the client application can send a request to create a new transaction by providing relevant details such as the payment amount, sender and receiver. GrailPay will then return a UUID, which serves as the unique identifier and can be used to fetch the details and status of the transaction. Please note that only one transaction can be created per request.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');



$apiInstance = new TheLogicStudio\GrailPay\Api\TransactionsApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client()
);
$create_transaction = new \TheLogicStudio\GrailPay\Model\CreateTransaction(); // \TheLogicStudio\GrailPay\Model\CreateTransaction

try {
    $result = $apiInstance->postTransaction($create_transaction);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling TransactionsApi->postTransaction: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **create_transaction** | [**\TheLogicStudio\GrailPay\Model\CreateTransaction**](../Model/CreateTransaction.md)|  | |

### Return type

[**\TheLogicStudio\GrailPay\Model\PostTransaction201Response**](../Model/PostTransaction201Response.md)

### Authorization

No authorization required

### HTTP request headers

- **Content-Type**: `application/json`
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)
