# TheLogicStudio\GrailPay\TransactionsApi

API Endpoints used for creating and managing transactions.

All URIs are relative to https://api.grailpay.com, except if the operation defines another base path.

| Method | HTTP request | Description |
| ------------- | ------------- | ------------- |
| [**deleteTransactionsByUuidCancel()**](TransactionsApi.md#deleteTransactionsByUuidCancel) | **DELETE** /api/v3/transactions/{uuid}/cancel | Cancel a transaction in the ACH application |
| [**getTransactions()**](TransactionsApi.md#getTransactions) | **GET** /api/v3/transactions | Get All Transactions |
| [**getTransactionsByUuid()**](TransactionsApi.md#getTransactionsByUuid) | **GET** /api/v3/transactions/{uuid} | Get Transaction |
| [**postTransactions()**](TransactionsApi.md#postTransactions) | **POST** /api/v3/transactions | Create Transaction |
| [**postTransactionsByUuidPause()**](TransactionsApi.md#postTransactionsByUuidPause) | **POST** /api/v3/transactions/{uuid}/pause | Pause a transaction in the ACH application |
| [**postTransactionsByUuidResume()**](TransactionsApi.md#postTransactionsByUuidResume) | **POST** /api/v3/transactions/{uuid}/resume | Resume a transaction in the ACH application |


## `deleteTransactionsByUuidCancel()`

```php
deleteTransactionsByUuidCancel($uuid): \TheLogicStudio\GrailPay\Model\PutBankAccountsByUuidDefault200Response
```

Cancel a transaction in the ACH application

This endpoint allows to cancel a transaction in the GrailPay ACH API Ecosystem.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (Token) authorization: ApiToken
$config = TheLogicStudio\GrailPay\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new TheLogicStudio\GrailPay\Api\TransactionsApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$uuid = 3fa85f64-5717-4562-b3fc-2c963f66afa6; // string | The UUID of the transaction to cancel.

try {
    $result = $apiInstance->deleteTransactionsByUuidCancel($uuid);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling TransactionsApi->deleteTransactionsByUuidCancel: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **uuid** | **string**| The UUID of the transaction to cancel. | |

### Return type

[**\TheLogicStudio\GrailPay\Model\PutBankAccountsByUuidDefault200Response**](../Model/PutBankAccountsByUuidDefault200Response.md)

### Authorization

[ApiToken](../../README.md#ApiToken)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `getTransactions()`

```php
getTransactions($filter_uuid, $filter_status, $filter_ach_id, $filter_r_code, $filter_client_reference_id, $filter_start_date, $filter_end_date, $filter_amount, $filter_merchant_uuid, $filter_person_uuid, $filter_payout_uuid, $sort, $page, $per_page): \TheLogicStudio\GrailPay\Model\GetTransactions200Response
```

Get All Transactions

This endpoint provides a paginated list of transactions visible to the authenticated user, with filtering and sorting options.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (Token) authorization: ApiToken
$config = TheLogicStudio\GrailPay\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new TheLogicStudio\GrailPay\Api\TransactionsApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$filter_uuid = 3fa85f64-5717-4562-b3fc-2c963f66afa6; // string | Filter by transaction UUID
$filter_status = CAPTURE_COMPLETE; // string | Filter by transaction status
$filter_ach_id = ach_1331Ds7MrGmp8iCkEFFdmR; // string | Filter by ACH trace ID
$filter_r_code = R01; // string | Filter by ACH return code on the transaction or its payout
$filter_client_reference_id = reference_12345; // string | Filter by client reference ID (partial match)
$filter_start_date = Mon Jan 01 13:00:00 NZDT 2024; // \DateTime | Filter transactions created on or after this date (YYYY-MM-DD)
$filter_end_date = Tue Dec 31 13:00:00 NZDT 2024; // \DateTime | Filter transactions created on or before this date (YYYY-MM-DD)
$filter_amount = >=100; // string | Filter by amount. Supports dynamic operators (e.g. filter[amount]=100, filter[amount]=>100, filter[amount]=<=500)
$filter_merchant_uuid = 6a8fc154-1a50-483b-a690-fd1dfaf9408b; // string | Filter by payee or payer merchant/business UUID
$filter_person_uuid = 019e0834-c96a-7d71-bb60-bda7b9a26d1a; // string | Filter by payee or payer person UUID
$filter_payout_uuid = a1e52556-7b0e-40d1-a787-9af5df215a57; // string | Filter by payout UUID (regular payout or processor payout). Results are limited to transactions the authenticated user can see.
$sort = -created_at; // string | Sort by field (created_at, amount). Prefix with '-' for descending order
$page = 1; // int | Page number for pagination
$per_page = 15; // int | Number of records per page

try {
    $result = $apiInstance->getTransactions($filter_uuid, $filter_status, $filter_ach_id, $filter_r_code, $filter_client_reference_id, $filter_start_date, $filter_end_date, $filter_amount, $filter_merchant_uuid, $filter_person_uuid, $filter_payout_uuid, $sort, $page, $per_page);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling TransactionsApi->getTransactions: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **filter_uuid** | **string**| Filter by transaction UUID | [optional] |
| **filter_status** | **string**| Filter by transaction status | [optional] |
| **filter_ach_id** | **string**| Filter by ACH trace ID | [optional] |
| **filter_r_code** | **string**| Filter by ACH return code on the transaction or its payout | [optional] |
| **filter_client_reference_id** | **string**| Filter by client reference ID (partial match) | [optional] |
| **filter_start_date** | **\DateTime**| Filter transactions created on or after this date (YYYY-MM-DD) | [optional] |
| **filter_end_date** | **\DateTime**| Filter transactions created on or before this date (YYYY-MM-DD) | [optional] |
| **filter_amount** | **string**| Filter by amount. Supports dynamic operators (e.g. filter[amount]&#x3D;100, filter[amount]&#x3D;&gt;100, filter[amount]&#x3D;&lt;&#x3D;500) | [optional] |
| **filter_merchant_uuid** | **string**| Filter by payee or payer merchant/business UUID | [optional] |
| **filter_person_uuid** | **string**| Filter by payee or payer person UUID | [optional] |
| **filter_payout_uuid** | **string**| Filter by payout UUID (regular payout or processor payout). Results are limited to transactions the authenticated user can see. | [optional] |
| **sort** | **string**| Sort by field (created_at, amount). Prefix with &#39;-&#39; for descending order | [optional] |
| **page** | **int**| Page number for pagination | [optional] |
| **per_page** | **int**| Number of records per page | [optional] [default to 15] |

### Return type

[**\TheLogicStudio\GrailPay\Model\GetTransactions200Response**](../Model/GetTransactions200Response.md)

### Authorization

[ApiToken](../../README.md#ApiToken)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `getTransactionsByUuid()`

```php
getTransactionsByUuid($uuid): \TheLogicStudio\GrailPay\Model\GetTransactionsByUuid200Response
```

Get Transaction

This endpoint returns the details of a single transaction along with its payout, refunds and clawback. The UUID is generated when the transaction is created and is associated with the transaction record.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (Token) authorization: ApiToken
$config = TheLogicStudio\GrailPay\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new TheLogicStudio\GrailPay\Api\TransactionsApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$uuid = 3fa85f64-5717-4562-b3fc-2c963f66afa6; // string | transaction UUID

try {
    $result = $apiInstance->getTransactionsByUuid($uuid);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling TransactionsApi->getTransactionsByUuid: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **uuid** | **string**| transaction UUID | |

### Return type

[**\TheLogicStudio\GrailPay\Model\GetTransactionsByUuid200Response**](../Model/GetTransactionsByUuid200Response.md)

### Authorization

[ApiToken](../../README.md#ApiToken)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `postTransactions()`

```php
postTransactions($post_transactions_request): \TheLogicStudio\GrailPay\Model\PostTransactions201Response
```

Create Transaction

Creates a queued ACH debit transaction between a payor and payee using entity UUIDs. Optional modality controls debit (transaction) ACH speed and credit (payout) rail/speed. When modality.payout is omitted, the server resolves and stores a default payout modality. modality.payout is rejected when the vendor uses processor batch payouts. Supports idempotency via Idempotency-Key header.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (Token) authorization: ApiToken
$config = TheLogicStudio\GrailPay\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new TheLogicStudio\GrailPay\Api\TransactionsApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$post_transactions_request = new \TheLogicStudio\GrailPay\Model\PostTransactionsRequest(); // \TheLogicStudio\GrailPay\Model\PostTransactionsRequest | Transaction creation payload. Authenticate with Authorization: Bearer <API_TOKEN>. Optional X-Request-ID may be supplied for request tracing. Optional Idempotency-Key may be supplied to safely retry the same create request; reuse of a key with a different payload returns 409.

try {
    $result = $apiInstance->postTransactions($post_transactions_request);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling TransactionsApi->postTransactions: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **post_transactions_request** | [**\TheLogicStudio\GrailPay\Model\PostTransactionsRequest**](../Model/PostTransactionsRequest.md)| Transaction creation payload. Authenticate with Authorization: Bearer &lt;API_TOKEN&gt;. Optional X-Request-ID may be supplied for request tracing. Optional Idempotency-Key may be supplied to safely retry the same create request; reuse of a key with a different payload returns 409. | |

### Return type

[**\TheLogicStudio\GrailPay\Model\PostTransactions201Response**](../Model/PostTransactions201Response.md)

### Authorization

[ApiToken](../../README.md#ApiToken)

### HTTP request headers

- **Content-Type**: `application/json`
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `postTransactionsByUuidPause()`

```php
postTransactionsByUuidPause($uuid): \TheLogicStudio\GrailPay\Model\PostTransactionsByUuidPause200Response
```

Pause a transaction in the ACH application

This endpoint allows to pause a transaction in the GrailPay ACH API Ecosystem.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (Token) authorization: ApiToken
$config = TheLogicStudio\GrailPay\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new TheLogicStudio\GrailPay\Api\TransactionsApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$uuid = 3fa85f64-5717-4562-b3fc-2c963f66afa6; // string | The UUID of the transaction to pause.

try {
    $result = $apiInstance->postTransactionsByUuidPause($uuid);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling TransactionsApi->postTransactionsByUuidPause: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **uuid** | **string**| The UUID of the transaction to pause. | |

### Return type

[**\TheLogicStudio\GrailPay\Model\PostTransactionsByUuidPause200Response**](../Model/PostTransactionsByUuidPause200Response.md)

### Authorization

[ApiToken](../../README.md#ApiToken)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `postTransactionsByUuidResume()`

```php
postTransactionsByUuidResume($uuid): \TheLogicStudio\GrailPay\Model\PostTransactionsByUuidResume200Response
```

Resume a transaction in the ACH application

This endpoint allows to resume a paused transaction in the GrailPay ACH API Ecosystem.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (Token) authorization: ApiToken
$config = TheLogicStudio\GrailPay\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new TheLogicStudio\GrailPay\Api\TransactionsApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$uuid = 3fa85f64-5717-4562-b3fc-2c963f66afa6; // string | The UUID of the transaction to resume.

try {
    $result = $apiInstance->postTransactionsByUuidResume($uuid);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling TransactionsApi->postTransactionsByUuidResume: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **uuid** | **string**| The UUID of the transaction to resume. | |

### Return type

[**\TheLogicStudio\GrailPay\Model\PostTransactionsByUuidResume200Response**](../Model/PostTransactionsByUuidResume200Response.md)

### Authorization

[ApiToken](../../README.md#ApiToken)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)
