# TheLogicStudio\GrailPay\StableApi

Stable, up-to-date APIs that are recommended for current integration.

All URIs are relative to https://api.grailpay.com, except if the operation defines another base path.

| Method | HTTP request | Description |
| ------------- | ------------- | ------------- |
| [**deleteBankAccounts()**](StableApi.md#deleteBankAccounts) | **DELETE** /3p/api/v2/bank-accounts/{aggregator_type}/{account_uuid} | Delete a bank account ( STABLE ) |
| [**deleteTransactions()**](StableApi.md#deleteTransactions) | **DELETE** /3p/api/v2/transactions/{uuid} | Cancel a transaction ( STABLE ) |
| [**deleteUsers()**](StableApi.md#deleteUsers) | **DELETE** /3p/api/v2/users/{uuid} | Deleting a User ( STABLE ) |
| [**deleteWebhook()**](StableApi.md#deleteWebhook) | **DELETE** /3p/api/v1/webhook | De-register Webhook ( STABLE ) |
| [**getBankAccount()**](StableApi.md#getBankAccount) | **GET** /3p/api/v1/bank-account/{user_uuid} | Get bank account details ( STABLE ) |
| [**getBankAccountsHistory()**](StableApi.md#getBankAccountsHistory) | **GET** /3p/api/v2/bank-accounts/{aggregator_type}/{account_uuid}/history | Fetch the transaction history for a bank account. ( STABLE ) |
| [**getBatchPayoutsBusiness()**](StableApi.md#getBatchPayoutsBusiness) | **GET** /3p/api/v2/batch-payouts/business/{business_user_uuid}/{batch_payout_uuid} | Get Business Batch Payout ( STABLE ) |
| [**getBatchPayoutsMerchant()**](StableApi.md#getBatchPayoutsMerchant) | **GET** /3p/api/v2/batch-payouts/merchant/{merchant_user_uuid}/{batch_payout_uuid} | Get Merchant Batch Payout ( STABLE ) |
| [**getBatchPayoutsPerson()**](StableApi.md#getBatchPayoutsPerson) | **GET** /3p/api/v2/batch-payouts/person/{user_uuid}/{batch_payout_uuid} | Get Person Batch Payout ( STABLE ) |
| [**getBatchPayoutsProcessor()**](StableApi.md#getBatchPayoutsProcessor) | **GET** /3p/api/v2/batch-payouts/processor/{batch_payout_uuid} | Get Processor Batch Payout ( STABLE ) |
| [**getBatchRefunds()**](StableApi.md#getBatchRefunds) | **GET** /3p/api/v2/batch-refunds | Get All Batch Refunds ( STABLE ) |
| [**getBusinesses()**](StableApi.md#getBusinesses) | **GET** /api/v3/businesses | Get All Businesses ( STABLE ) |
| [**getMerchants()**](StableApi.md#getMerchants) | **GET** /api/v3/merchants | Get All Merchants ( STABLE ) |
| [**getMerchantsBilling()**](StableApi.md#getMerchantsBilling) | **GET** /3p/api/v2/merchants/{uuid}/billing | Get Billing by Merchant User UUID ( STABLE ) |
| [**getPeople()**](StableApi.md#getPeople) | **GET** /api/v3/people | Get All People ( STABLE ) |
| [**getTransactions()**](StableApi.md#getTransactions) | **GET** /3p/api/v2/transactions | Get Transactions ( STABLE ) |
| [**getTransactionsRefunds()**](StableApi.md#getTransactionsRefunds) | **GET** /3p/api/v1/transactions/{transaction_uuid}/refunds | Get Transaction Refunds ( STABLE ) |
| [**getUsersBankAccounts()**](StableApi.md#getUsersBankAccounts) | **GET** /3p/api/v2/users/{uuid}/bank-accounts | Get all bank accounts for a user ( STABLE ) |
| [**getUsersBankAccountsBalance()**](StableApi.md#getUsersBankAccountsBalance) | **GET** /3p/api/v2/users/{uuid}/bank-accounts/{account_uuid}/balance | Fetch the bank account balance ( STABLE ) |
| [**getWebhook()**](StableApi.md#getWebhook) | **GET** /3p/api/v1/webhook | Get registered webhooks ( STABLE ) |
| [**patchBusinesses()**](StableApi.md#patchBusinesses) | **PATCH** /api/v3/businesses/{uuid} | Update a Business into the ACH application ( STABLE ) |
| [**patchMerchants()**](StableApi.md#patchMerchants) | **PATCH** /api/v3/merchants/{uuid} | Update a Merchant into the ACH application ( STABLE ) |
| [**patchPeople()**](StableApi.md#patchPeople) | **PATCH** /api/v3/people/{uuid} | Update a Person into the ACH application ( STABLE ) |
| [**postBankAccountBalance()**](StableApi.md#postBankAccountBalance) | **POST** /3p/api/v1/bank-account/balance/{user_uuid} | Get balance approval ( STABLE ) |
| [**postBankAccountUser()**](StableApi.md#postBankAccountUser) | **POST** /3p/api/v1/bank-account/user | Get User Details by bank account ( STABLE ) |
| [**postBankAccountsValidate()**](StableApi.md#postBankAccountsValidate) | **POST** /3p/api/v2/bank-accounts/validate | Validate bank account and routing number ( STABLE ) |
| [**postBusinesses()**](StableApi.md#postBusinesses) | **POST** /api/v3/businesses | Onboard a new Business into the ACH application ( STABLE ) |
| [**postMerchants()**](StableApi.md#postMerchants) | **POST** /api/v3/merchants | Onboard a new Merchant into the ACH application ( STABLE ) |
| [**postPeople()**](StableApi.md#postPeople) | **POST** /api/v3/people | Onboard a new Person into the ACH application ( STABLE ) |
| [**postPeopleBankAccounts()**](StableApi.md#postPeopleBankAccounts) | **POST** /api/v3/people/{uuid}/bank-accounts | Onboard a new Person into the ACH application ( STABLE ) |
| [**postTransaction()**](StableApi.md#postTransaction) | **POST** /3p/api/v1/transaction | Create a new transaction ( STABLE ) |
| [**postTransactionsRefund()**](StableApi.md#postTransactionsRefund) | **POST** /3p/api/v1/transactions/{uuid}/refund | Refund a transaction ( STABLE ) |
| [**postWebhook()**](StableApi.md#postWebhook) | **POST** /3p/api/v1/webhook | Register Webhook ( STABLE ) |
| [**putBankAccountSwitchDefault()**](StableApi.md#putBankAccountSwitchDefault) | **PUT** /3p/api/v1/bank-account/switch/default/{user_uuid} | Switch default bank account ( STABLE ) |


## `deleteBankAccounts()`

```php
deleteBankAccounts($aggregator_type, $account_uuid): \TheLogicStudio\GrailPay\Model\DeleteBankAccounts200Response
```

Delete a bank account ( STABLE )

Deletes a bank account by its UUID and aggregator type.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');



$apiInstance = new TheLogicStudio\GrailPay\Api\StableApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client()
);
$aggregator_type = 'aggregator_type_example'; // string | The type of the bank aggregator
$account_uuid = 'account_uuid_example'; // string | The UUID of the bank account

try {
    $result = $apiInstance->deleteBankAccounts($aggregator_type, $account_uuid);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling StableApi->deleteBankAccounts: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **aggregator_type** | **string**| The type of the bank aggregator | |
| **account_uuid** | **string**| The UUID of the bank account | |

### Return type

[**\TheLogicStudio\GrailPay\Model\DeleteBankAccounts200Response**](../Model/DeleteBankAccounts200Response.md)

### Authorization

No authorization required

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

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



$apiInstance = new TheLogicStudio\GrailPay\Api\StableApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client()
);
$uuid = 'uuid_example'; // string | UUID of the transaction to cancel

try {
    $result = $apiInstance->deleteTransactions($uuid);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling StableApi->deleteTransactions: ', $e->getMessage(), PHP_EOL;
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

## `deleteUsers()`

```php
deleteUsers($uuid): \TheLogicStudio\GrailPay\Model\DeleteUsers200Response
```

Deleting a User ( STABLE )

This API deletes a specific user from the system based on their unique user UUID.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');



$apiInstance = new TheLogicStudio\GrailPay\Api\StableApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client()
);
$uuid = 'uuid_example'; // string | User UUID

try {
    $result = $apiInstance->deleteUsers($uuid);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling StableApi->deleteUsers: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **uuid** | **string**| User UUID | |

### Return type

[**\TheLogicStudio\GrailPay\Model\DeleteUsers200Response**](../Model/DeleteUsers200Response.md)

### Authorization

No authorization required

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `deleteWebhook()`

```php
deleteWebhook($v1_de_register_webhook_request): \TheLogicStudio\GrailPay\Model\DeleteWebhook200Response
```

De-register Webhook ( STABLE )

Deregistering a webhook via API involves removing a previously registered webhook configuration from the GrailPay. To disable notification related to particular transaction events, you need to de-register webhook with registered events name.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');



$apiInstance = new TheLogicStudio\GrailPay\Api\StableApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client()
);
$v1_de_register_webhook_request = new \TheLogicStudio\GrailPay\Model\V1DeRegisterWebhookRequest(); // \TheLogicStudio\GrailPay\Model\V1DeRegisterWebhookRequest

try {
    $result = $apiInstance->deleteWebhook($v1_de_register_webhook_request);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling StableApi->deleteWebhook: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **v1_de_register_webhook_request** | [**\TheLogicStudio\GrailPay\Model\V1DeRegisterWebhookRequest**](../Model/V1DeRegisterWebhookRequest.md)|  | |

### Return type

[**\TheLogicStudio\GrailPay\Model\DeleteWebhook200Response**](../Model/DeleteWebhook200Response.md)

### Authorization

No authorization required

### HTTP request headers

- **Content-Type**: `application/json`
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `getBankAccount()`

```php
getBankAccount($user_uuid): \TheLogicStudio\GrailPay\Model\GetBankAccount200Response
```

Get bank account details ( STABLE )

Retrieve the bank account details for a specific user.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');



$apiInstance = new TheLogicStudio\GrailPay\Api\StableApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client()
);
$user_uuid = 'user_uuid_example'; // string | UUID of the user

try {
    $result = $apiInstance->getBankAccount($user_uuid);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling StableApi->getBankAccount: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **user_uuid** | **string**| UUID of the user | |

### Return type

[**\TheLogicStudio\GrailPay\Model\GetBankAccount200Response**](../Model/GetBankAccount200Response.md)

### Authorization

No authorization required

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `getBankAccountsHistory()`

```php
getBankAccountsHistory($aggregator_type, $account_uuid): \TheLogicStudio\GrailPay\Model\GetBankAccountsHistory200Response
```

Fetch the transaction history for a bank account. ( STABLE )

Fetch a list of transactions for a bank account.  This currently only works with accounts linked through the Bank Link SDK.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');



$apiInstance = new TheLogicStudio\GrailPay\Api\StableApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client()
);
$aggregator_type = 'aggregator_type_example'; // string | Bank Account Provider.  Possible Values: bank_link
$account_uuid = 'account_uuid_example'; // string | UUID of the bank account

try {
    $result = $apiInstance->getBankAccountsHistory($aggregator_type, $account_uuid);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling StableApi->getBankAccountsHistory: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **aggregator_type** | **string**| Bank Account Provider.  Possible Values: bank_link | |
| **account_uuid** | **string**| UUID of the bank account | |

### Return type

[**\TheLogicStudio\GrailPay\Model\GetBankAccountsHistory200Response**](../Model/GetBankAccountsHistory200Response.md)

### Authorization

No authorization required

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `getBatchPayoutsBusiness()`

```php
getBatchPayoutsBusiness($business_user_uuid, $batch_payout_uuid): \TheLogicStudio\GrailPay\Model\V2PayeeBatchPayoutResponse
```

Get Business Batch Payout ( STABLE )

This API retrieves the details of a business batch payout using the business user UUID and the unique batch payout UUID. The response provides comprehensive information about the payout, including the total amount and a detailed breakdown of the transactions.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');



$apiInstance = new TheLogicStudio\GrailPay\Api\StableApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client()
);
$business_user_uuid = 'business_user_uuid_example'; // string | UUID of the business user
$batch_payout_uuid = 'batch_payout_uuid_example'; // string | UUID of the batch payout

try {
    $result = $apiInstance->getBatchPayoutsBusiness($business_user_uuid, $batch_payout_uuid);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling StableApi->getBatchPayoutsBusiness: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **business_user_uuid** | **string**| UUID of the business user | |
| **batch_payout_uuid** | **string**| UUID of the batch payout | |

### Return type

[**\TheLogicStudio\GrailPay\Model\V2PayeeBatchPayoutResponse**](../Model/V2PayeeBatchPayoutResponse.md)

### Authorization

No authorization required

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `getBatchPayoutsMerchant()`

```php
getBatchPayoutsMerchant($merchant_user_uuid, $batch_payout_uuid): \TheLogicStudio\GrailPay\Model\V2PayeeBatchPayoutResponse
```

Get Merchant Batch Payout ( STABLE )

This API retrieves the details of a merchant batch payout using the merchant user UUID and the unique batch payout UUID. The response provides comprehensive information about the payout, including the total amount and a detailed breakdown of the transactions.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');



$apiInstance = new TheLogicStudio\GrailPay\Api\StableApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client()
);
$merchant_user_uuid = 'merchant_user_uuid_example'; // string | UUID of the merchant
$batch_payout_uuid = 'batch_payout_uuid_example'; // string | UUID of the batch payout

try {
    $result = $apiInstance->getBatchPayoutsMerchant($merchant_user_uuid, $batch_payout_uuid);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling StableApi->getBatchPayoutsMerchant: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **merchant_user_uuid** | **string**| UUID of the merchant | |
| **batch_payout_uuid** | **string**| UUID of the batch payout | |

### Return type

[**\TheLogicStudio\GrailPay\Model\V2PayeeBatchPayoutResponse**](../Model/V2PayeeBatchPayoutResponse.md)

### Authorization

No authorization required

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `getBatchPayoutsPerson()`

```php
getBatchPayoutsPerson($user_uuid, $batch_payout_uuid): \TheLogicStudio\GrailPay\Model\V2PayeeBatchPayoutResponse
```

Get Person Batch Payout ( STABLE )

This API retrieves the details of a person batch payout using the person user UUID and the unique batch payout UUID. The response provides comprehensive information about the payout, including the total amount and a detailed breakdown of the transactions.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');



$apiInstance = new TheLogicStudio\GrailPay\Api\StableApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client()
);
$user_uuid = 'user_uuid_example'; // string | UUID of the user
$batch_payout_uuid = 'batch_payout_uuid_example'; // string | UUID of the batch payout

try {
    $result = $apiInstance->getBatchPayoutsPerson($user_uuid, $batch_payout_uuid);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling StableApi->getBatchPayoutsPerson: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **user_uuid** | **string**| UUID of the user | |
| **batch_payout_uuid** | **string**| UUID of the batch payout | |

### Return type

[**\TheLogicStudio\GrailPay\Model\V2PayeeBatchPayoutResponse**](../Model/V2PayeeBatchPayoutResponse.md)

### Authorization

No authorization required

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `getBatchPayoutsProcessor()`

```php
getBatchPayoutsProcessor($batch_payout_uuid): \TheLogicStudio\GrailPay\Model\V2ProcessorBatchPayoutResponse
```

Get Processor Batch Payout ( STABLE )

This API retrieves the details of a processor batch payout using the unique batch payout UUID. The response provides comprehensive information about the payout, including the total amount and a detailed breakdown of the transactions.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');



$apiInstance = new TheLogicStudio\GrailPay\Api\StableApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client()
);
$batch_payout_uuid = 'batch_payout_uuid_example'; // string | UUID of the batch payout

try {
    $result = $apiInstance->getBatchPayoutsProcessor($batch_payout_uuid);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling StableApi->getBatchPayoutsProcessor: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **batch_payout_uuid** | **string**| UUID of the batch payout | |

### Return type

[**\TheLogicStudio\GrailPay\Model\V2ProcessorBatchPayoutResponse**](../Model/V2ProcessorBatchPayoutResponse.md)

### Authorization

No authorization required

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

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



$apiInstance = new TheLogicStudio\GrailPay\Api\StableApi(
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
    echo 'Exception when calling StableApi->getBatchRefunds: ', $e->getMessage(), PHP_EOL;
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

## `getBusinesses()`

```php
getBusinesses($filter_uuid, $filter_name, $sort, $page, $per_page): \TheLogicStudio\GrailPay\Model\GetBusinesses200Response
```

Get All Businesses ( STABLE )

This endpoint provides a comprehensive list of all registered businesses, including essential details. Pagination options are available to efficiently manage large datasets.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');



$apiInstance = new TheLogicStudio\GrailPay\Api\StableApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client()
);
$filter_uuid = 7c41f6a2-a4b9-4df8-9225-2c1b7312042e; // string | Filter by business UUID
$filter_name = John Inc; // string | Filter by business name
$sort = -created_at; // string | Sort by field (created_at, name). Prefix with '-' for descending order
$page = 1; // int | Page number for pagination
$per_page = 15; // int | Number of records per page

try {
    $result = $apiInstance->getBusinesses($filter_uuid, $filter_name, $sort, $page, $per_page);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling StableApi->getBusinesses: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **filter_uuid** | **string**| Filter by business UUID | [optional] |
| **filter_name** | **string**| Filter by business name | [optional] |
| **sort** | **string**| Sort by field (created_at, name). Prefix with &#39;-&#39; for descending order | [optional] |
| **page** | **int**| Page number for pagination | [optional] |
| **per_page** | **int**| Number of records per page | [optional] [default to 15] |

### Return type

[**\TheLogicStudio\GrailPay\Model\GetBusinesses200Response**](../Model/GetBusinesses200Response.md)

### Authorization

No authorization required

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `getMerchants()`

```php
getMerchants($filter_uuid, $filter_name, $filter_tin, $sort, $page, $per_page): \TheLogicStudio\GrailPay\Model\GetMerchants200Response
```

Get All Merchants ( STABLE )

This endpoint provides a comprehensive list of all registered merchants, including essential details. Pagination options are available to efficiently manage large datasets.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');



$apiInstance = new TheLogicStudio\GrailPay\Api\StableApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client()
);
$filter_uuid = 7c41f6a2-a4b9-4df8-9225-2c1b7312042e; // string | Filter by merchant UUID
$filter_name = John Inc; // string | Filter by merchant name
$filter_tin = 123456789; // string | Filter by EIN (TIN) number
$sort = -created_at; // string | Sort by field (created_at, name). Prefix with '-' for descending order
$page = 1; // int | Page number for pagination
$per_page = 15; // int | Number of records per page

try {
    $result = $apiInstance->getMerchants($filter_uuid, $filter_name, $filter_tin, $sort, $page, $per_page);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling StableApi->getMerchants: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **filter_uuid** | **string**| Filter by merchant UUID | [optional] |
| **filter_name** | **string**| Filter by merchant name | [optional] |
| **filter_tin** | **string**| Filter by EIN (TIN) number | [optional] |
| **sort** | **string**| Sort by field (created_at, name). Prefix with &#39;-&#39; for descending order | [optional] |
| **page** | **int**| Page number for pagination | [optional] |
| **per_page** | **int**| Number of records per page | [optional] [default to 15] |

### Return type

[**\TheLogicStudio\GrailPay\Model\GetMerchants200Response**](../Model/GetMerchants200Response.md)

### Authorization

No authorization required

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `getMerchantsBilling()`

```php
getMerchantsBilling($uuid, $start_date, $end_date): \TheLogicStudio\GrailPay\Model\GetMerchantsBilling200Response
```

Get Billing by Merchant User UUID ( STABLE )

This retrieves a summary of all billed events for a specific merchant, providing comprehensive billing details to support seamless integration.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');



$apiInstance = new TheLogicStudio\GrailPay\Api\StableApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client()
);
$uuid = 'uuid_example'; // string | UUID of the merchant user
$start_date = new \DateTime('2013-10-20T19:20:30+01:00'); // \DateTime | Start date for billing summary (YYYY-MM-DD)
$end_date = new \DateTime('2013-10-20T19:20:30+01:00'); // \DateTime | End date for billing summary (YYYY-MM-DD)

try {
    $result = $apiInstance->getMerchantsBilling($uuid, $start_date, $end_date);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling StableApi->getMerchantsBilling: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **uuid** | **string**| UUID of the merchant user | |
| **start_date** | **\DateTime**| Start date for billing summary (YYYY-MM-DD) | [optional] |
| **end_date** | **\DateTime**| End date for billing summary (YYYY-MM-DD) | [optional] |

### Return type

[**\TheLogicStudio\GrailPay\Model\GetMerchantsBilling200Response**](../Model/GetMerchantsBilling200Response.md)

### Authorization

No authorization required

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `getPeople()`

```php
getPeople($filter_uuid, $filter_client_reference_id, $filter_first_name, $filter_last_name, $sort, $page, $per_page): \TheLogicStudio\GrailPay\Model\GetPeople200Response
```

Get All People ( STABLE )

This endpoint provides a comprehensive list of all registered people, including essential details. Pagination options are available to efficiently manage large datasets.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');



$apiInstance = new TheLogicStudio\GrailPay\Api\StableApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client()
);
$filter_uuid = 7c41f6a2-a4b9-4df8-9225-2c1b7312042e; // string | Filter by person UUID
$filter_client_reference_id = reference_12345; // string | Filter by client reference ID
$filter_first_name = John; // string | Filter by first name
$filter_last_name = Doe; // string | Filter by last name
$sort = -created_at; // string | Sort by field (created_at, first_name, last_name). Prefix with '-' for descending order
$page = 1; // int | Page number for pagination
$per_page = 15; // int | Number of records per page

try {
    $result = $apiInstance->getPeople($filter_uuid, $filter_client_reference_id, $filter_first_name, $filter_last_name, $sort, $page, $per_page);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling StableApi->getPeople: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **filter_uuid** | **string**| Filter by person UUID | [optional] |
| **filter_client_reference_id** | **string**| Filter by client reference ID | [optional] |
| **filter_first_name** | **string**| Filter by first name | [optional] |
| **filter_last_name** | **string**| Filter by last name | [optional] |
| **sort** | **string**| Sort by field (created_at, first_name, last_name). Prefix with &#39;-&#39; for descending order | [optional] |
| **page** | **int**| Page number for pagination | [optional] |
| **per_page** | **int**| Number of records per page | [optional] [default to 15] |

### Return type

[**\TheLogicStudio\GrailPay\Model\GetPeople200Response**](../Model/GetPeople200Response.md)

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



$apiInstance = new TheLogicStudio\GrailPay\Api\StableApi(
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
    echo 'Exception when calling StableApi->getTransactions: ', $e->getMessage(), PHP_EOL;
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



$apiInstance = new TheLogicStudio\GrailPay\Api\StableApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client()
);
$transaction_uuid = 9c2af585-9fea-4c47-ac12-e00f42943cd8; // string | Transaction UUID

try {
    $result = $apiInstance->getTransactionsRefunds($transaction_uuid);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling StableApi->getTransactionsRefunds: ', $e->getMessage(), PHP_EOL;
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

## `getUsersBankAccounts()`

```php
getUsersBankAccounts($uuid): \TheLogicStudio\GrailPay\Model\GetUsersBankAccounts200Response
```

Get all bank accounts for a user ( STABLE )

This API retrieves a list of all bank accounts associated with a business or person. The response includes details such as the account number, routing number, account holder's name, account type, and other relevant information.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');



$apiInstance = new TheLogicStudio\GrailPay\Api\StableApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client()
);
$uuid = 'uuid_example'; // string | UUID of the user

try {
    $result = $apiInstance->getUsersBankAccounts($uuid);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling StableApi->getUsersBankAccounts: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **uuid** | **string**| UUID of the user | |

### Return type

[**\TheLogicStudio\GrailPay\Model\GetUsersBankAccounts200Response**](../Model/GetUsersBankAccounts200Response.md)

### Authorization

No authorization required

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `getUsersBankAccountsBalance()`

```php
getUsersBankAccountsBalance($uuid, $account_uuid): \TheLogicStudio\GrailPay\Model\GetUsersBankAccountsBalance200Response
```

Fetch the bank account balance ( STABLE )

Fetch the balance of a specific bank account for a user.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');



$apiInstance = new TheLogicStudio\GrailPay\Api\StableApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client()
);
$uuid = 'uuid_example'; // string | UUID of the user
$account_uuid = 'account_uuid_example'; // string | UUID of the bank account

try {
    $result = $apiInstance->getUsersBankAccountsBalance($uuid, $account_uuid);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling StableApi->getUsersBankAccountsBalance: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **uuid** | **string**| UUID of the user | |
| **account_uuid** | **string**| UUID of the bank account | |

### Return type

[**\TheLogicStudio\GrailPay\Model\GetUsersBankAccountsBalance200Response**](../Model/GetUsersBankAccountsBalance200Response.md)

### Authorization

No authorization required

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `getWebhook()`

```php
getWebhook(): \TheLogicStudio\GrailPay\Model\GetWebhook200Response
```

Get registered webhooks ( STABLE )

Retrieve a list of registered webhooks for the authenticated user.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');



$apiInstance = new TheLogicStudio\GrailPay\Api\StableApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client()
);

try {
    $result = $apiInstance->getWebhook();
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling StableApi->getWebhook: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

This endpoint does not need any parameter.

### Return type

[**\TheLogicStudio\GrailPay\Model\GetWebhook200Response**](../Model/GetWebhook200Response.md)

### Authorization

No authorization required

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `patchBusinesses()`

```php
patchBusinesses($uuid, $post_businesses_request): \TheLogicStudio\GrailPay\Model\PatchBusinesses200Response
```

Update a Business into the ACH application ( STABLE )

This endpoint allows for updating a Business to the GrailPay ACH API Ecosystem.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');



$apiInstance = new TheLogicStudio\GrailPay\Api\StableApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client()
);
$uuid = 'uuid_example'; // string
$post_businesses_request = new \TheLogicStudio\GrailPay\Model\PostBusinessesRequest(); // \TheLogicStudio\GrailPay\Model\PostBusinessesRequest

try {
    $result = $apiInstance->patchBusinesses($uuid, $post_businesses_request);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling StableApi->patchBusinesses: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **uuid** | **string**|  | |
| **post_businesses_request** | [**\TheLogicStudio\GrailPay\Model\PostBusinessesRequest**](../Model/PostBusinessesRequest.md)|  | |

### Return type

[**\TheLogicStudio\GrailPay\Model\PatchBusinesses200Response**](../Model/PatchBusinesses200Response.md)

### Authorization

No authorization required

### HTTP request headers

- **Content-Type**: `application/json`
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `patchMerchants()`

```php
patchMerchants($uuid, $post_merchants_request): \TheLogicStudio\GrailPay\Model\PatchMerchants200Response
```

Update a Merchant into the ACH application ( STABLE )

This endpoint allows for updating a Merchant to the GrailPay ACH API Ecosystem.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');



$apiInstance = new TheLogicStudio\GrailPay\Api\StableApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client()
);
$uuid = 'uuid_example'; // string
$post_merchants_request = new \TheLogicStudio\GrailPay\Model\PostMerchantsRequest(); // \TheLogicStudio\GrailPay\Model\PostMerchantsRequest

try {
    $result = $apiInstance->patchMerchants($uuid, $post_merchants_request);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling StableApi->patchMerchants: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **uuid** | **string**|  | |
| **post_merchants_request** | [**\TheLogicStudio\GrailPay\Model\PostMerchantsRequest**](../Model/PostMerchantsRequest.md)|  | |

### Return type

[**\TheLogicStudio\GrailPay\Model\PatchMerchants200Response**](../Model/PatchMerchants200Response.md)

### Authorization

No authorization required

### HTTP request headers

- **Content-Type**: `application/json`
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `patchPeople()`

```php
patchPeople($uuid, $post_people_request): \TheLogicStudio\GrailPay\Model\PatchPeople200Response
```

Update a Person into the ACH application ( STABLE )

This endpoint allows for updating a Person to the GrailPay ACH API Ecosystem.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');



$apiInstance = new TheLogicStudio\GrailPay\Api\StableApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client()
);
$uuid = 'uuid_example'; // string
$post_people_request = new \TheLogicStudio\GrailPay\Model\PostPeopleRequest(); // \TheLogicStudio\GrailPay\Model\PostPeopleRequest

try {
    $result = $apiInstance->patchPeople($uuid, $post_people_request);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling StableApi->patchPeople: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **uuid** | **string**|  | |
| **post_people_request** | [**\TheLogicStudio\GrailPay\Model\PostPeopleRequest**](../Model/PostPeopleRequest.md)|  | |

### Return type

[**\TheLogicStudio\GrailPay\Model\PatchPeople200Response**](../Model/PatchPeople200Response.md)

### Authorization

No authorization required

### HTTP request headers

- **Content-Type**: `application/json`
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `postBankAccountBalance()`

```php
postBankAccountBalance($user_uuid, $v1_get_bank_account_balance_request): \TheLogicStudio\GrailPay\Model\PostBankAccountBalance200Response
```

Get balance approval ( STABLE )

Retrieve the balance approval for a specific user.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');



$apiInstance = new TheLogicStudio\GrailPay\Api\StableApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client()
);
$user_uuid = 'user_uuid_example'; // string | UUID of the user
$v1_get_bank_account_balance_request = new \TheLogicStudio\GrailPay\Model\V1GetBankAccountBalanceRequest(); // \TheLogicStudio\GrailPay\Model\V1GetBankAccountBalanceRequest

try {
    $result = $apiInstance->postBankAccountBalance($user_uuid, $v1_get_bank_account_balance_request);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling StableApi->postBankAccountBalance: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **user_uuid** | **string**| UUID of the user | |
| **v1_get_bank_account_balance_request** | [**\TheLogicStudio\GrailPay\Model\V1GetBankAccountBalanceRequest**](../Model/V1GetBankAccountBalanceRequest.md)|  | |

### Return type

[**\TheLogicStudio\GrailPay\Model\PostBankAccountBalance200Response**](../Model/PostBankAccountBalance200Response.md)

### Authorization

No authorization required

### HTTP request headers

- **Content-Type**: `application/json`
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `postBankAccountUser()`

```php
postBankAccountUser($post_bank_account_user_request): \TheLogicStudio\GrailPay\Model\PostBankAccountUser200Response
```

Get User Details by bank account ( STABLE )

This API will return the details of the user associated with a specific bank account

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');



$apiInstance = new TheLogicStudio\GrailPay\Api\StableApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client()
);
$post_bank_account_user_request = new \TheLogicStudio\GrailPay\Model\PostBankAccountUserRequest(); // \TheLogicStudio\GrailPay\Model\PostBankAccountUserRequest

try {
    $result = $apiInstance->postBankAccountUser($post_bank_account_user_request);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling StableApi->postBankAccountUser: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **post_bank_account_user_request** | [**\TheLogicStudio\GrailPay\Model\PostBankAccountUserRequest**](../Model/PostBankAccountUserRequest.md)|  | |

### Return type

[**\TheLogicStudio\GrailPay\Model\PostBankAccountUser200Response**](../Model/PostBankAccountUser200Response.md)

### Authorization

No authorization required

### HTTP request headers

- **Content-Type**: `application/json`
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `postBankAccountsValidate()`

```php
postBankAccountsValidate($store_account_validation_request): \TheLogicStudio\GrailPay\Model\PostBankAccountsValidate200Response
```

Validate bank account and routing number ( STABLE )

GrailPay provides a standalone Account and Routing Number Validation API, allowing businesses to verify bank account details before onboarding an entity or processing transactions. Using this validation helps prevent failed transactions, failed payouts, and other payment issues by ensuring that the account and routing numbers provided are legitimate.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');



$apiInstance = new TheLogicStudio\GrailPay\Api\StableApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client()
);
$store_account_validation_request = new \TheLogicStudio\GrailPay\Model\StoreAccountValidationRequest(); // \TheLogicStudio\GrailPay\Model\StoreAccountValidationRequest

try {
    $result = $apiInstance->postBankAccountsValidate($store_account_validation_request);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling StableApi->postBankAccountsValidate: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **store_account_validation_request** | [**\TheLogicStudio\GrailPay\Model\StoreAccountValidationRequest**](../Model/StoreAccountValidationRequest.md)|  | |

### Return type

[**\TheLogicStudio\GrailPay\Model\PostBankAccountsValidate200Response**](../Model/PostBankAccountsValidate200Response.md)

### Authorization

No authorization required

### HTTP request headers

- **Content-Type**: `application/json`
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `postBusinesses()`

```php
postBusinesses($post_businesses_request): \TheLogicStudio\GrailPay\Model\PostBusinesses201Response
```

Onboard a new Business into the ACH application ( STABLE )

This endpoint allows for adding a new Business to the GrailPay ACH API Ecosystem.  The only item that is required is the Bank Account object, but we strongly encourage that you supply as much information as possible.  When including the bank account, you can pass either Plaid information or account and routing information.  You should never pass both.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');



$apiInstance = new TheLogicStudio\GrailPay\Api\StableApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client()
);
$post_businesses_request = new \TheLogicStudio\GrailPay\Model\PostBusinessesRequest(); // \TheLogicStudio\GrailPay\Model\PostBusinessesRequest

try {
    $result = $apiInstance->postBusinesses($post_businesses_request);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling StableApi->postBusinesses: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **post_businesses_request** | [**\TheLogicStudio\GrailPay\Model\PostBusinessesRequest**](../Model/PostBusinessesRequest.md)|  | |

### Return type

[**\TheLogicStudio\GrailPay\Model\PostBusinesses201Response**](../Model/PostBusinesses201Response.md)

### Authorization

No authorization required

### HTTP request headers

- **Content-Type**: `application/json`
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `postMerchants()`

```php
postMerchants($post_merchants_request): \TheLogicStudio\GrailPay\Model\PostMerchants201Response
```

Onboard a new Merchant into the ACH application ( STABLE )

This endpoint allows for adding a new Merchant to the GrailPay ACH API Ecosystem.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');



$apiInstance = new TheLogicStudio\GrailPay\Api\StableApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client()
);
$post_merchants_request = new \TheLogicStudio\GrailPay\Model\PostMerchantsRequest(); // \TheLogicStudio\GrailPay\Model\PostMerchantsRequest

try {
    $result = $apiInstance->postMerchants($post_merchants_request);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling StableApi->postMerchants: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **post_merchants_request** | [**\TheLogicStudio\GrailPay\Model\PostMerchantsRequest**](../Model/PostMerchantsRequest.md)|  | |

### Return type

[**\TheLogicStudio\GrailPay\Model\PostMerchants201Response**](../Model/PostMerchants201Response.md)

### Authorization

No authorization required

### HTTP request headers

- **Content-Type**: `application/json`
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `postPeople()`

```php
postPeople($post_people_request): \TheLogicStudio\GrailPay\Model\PostPeople201Response
```

Onboard a new Person into the ACH application ( STABLE )

This endpoint allows for adding a new Person to the GrailPay ACH API Ecosystem.  The only item that is required is the Bank Account object, but we strongly encourage that you supply as much information as possible.  When including the bank account, you can pass either Plaid information or account and routing information.  You should never pass both.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');



$apiInstance = new TheLogicStudio\GrailPay\Api\StableApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client()
);
$post_people_request = new \TheLogicStudio\GrailPay\Model\PostPeopleRequest(); // \TheLogicStudio\GrailPay\Model\PostPeopleRequest

try {
    $result = $apiInstance->postPeople($post_people_request);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling StableApi->postPeople: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **post_people_request** | [**\TheLogicStudio\GrailPay\Model\PostPeopleRequest**](../Model/PostPeopleRequest.md)|  | |

### Return type

[**\TheLogicStudio\GrailPay\Model\PostPeople201Response**](../Model/PostPeople201Response.md)

### Authorization

No authorization required

### HTTP request headers

- **Content-Type**: `application/json`
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `postPeopleBankAccounts()`

```php
postPeopleBankAccounts($uuid, $post_people_bank_accounts_request): \TheLogicStudio\GrailPay\Model\PostPeopleBankAccounts200Response
```

Onboard a new Person into the ACH application ( STABLE )

This endpoint allows for adding a new Bank Account to the GrailPay ACH API Ecosystem. The only item that is required is the Bank Account object. When including the bank account, you can pass either Plaid information or account and routing information. You should never pass both.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');



$apiInstance = new TheLogicStudio\GrailPay\Api\StableApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client()
);
$uuid = 'uuid_example'; // string
$post_people_bank_accounts_request = new \TheLogicStudio\GrailPay\Model\PostPeopleBankAccountsRequest(); // \TheLogicStudio\GrailPay\Model\PostPeopleBankAccountsRequest

try {
    $result = $apiInstance->postPeopleBankAccounts($uuid, $post_people_bank_accounts_request);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling StableApi->postPeopleBankAccounts: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **uuid** | **string**|  | |
| **post_people_bank_accounts_request** | [**\TheLogicStudio\GrailPay\Model\PostPeopleBankAccountsRequest**](../Model/PostPeopleBankAccountsRequest.md)|  | |

### Return type

[**\TheLogicStudio\GrailPay\Model\PostPeopleBankAccounts200Response**](../Model/PostPeopleBankAccounts200Response.md)

### Authorization

No authorization required

### HTTP request headers

- **Content-Type**: `application/json`
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



$apiInstance = new TheLogicStudio\GrailPay\Api\StableApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client()
);
$create_transaction = new \TheLogicStudio\GrailPay\Model\CreateTransaction(); // \TheLogicStudio\GrailPay\Model\CreateTransaction

try {
    $result = $apiInstance->postTransaction($create_transaction);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling StableApi->postTransaction: ', $e->getMessage(), PHP_EOL;
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



$apiInstance = new TheLogicStudio\GrailPay\Api\StableApi(
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
    echo 'Exception when calling StableApi->postTransactionsRefund: ', $e->getMessage(), PHP_EOL;
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

## `postWebhook()`

```php
postWebhook($v1_register_webhook_request): \TheLogicStudio\GrailPay\Model\PostWebhook201Response
```

Register Webhook ( STABLE )

Registering a webhook via API call involves configuring a client application to receive notifications and updates from GrailPay. To enable notification related to transaction, you need to register webhook with sets of predefined Events.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');



$apiInstance = new TheLogicStudio\GrailPay\Api\StableApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client()
);
$v1_register_webhook_request = new \TheLogicStudio\GrailPay\Model\V1RegisterWebhookRequest(); // \TheLogicStudio\GrailPay\Model\V1RegisterWebhookRequest

try {
    $result = $apiInstance->postWebhook($v1_register_webhook_request);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling StableApi->postWebhook: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **v1_register_webhook_request** | [**\TheLogicStudio\GrailPay\Model\V1RegisterWebhookRequest**](../Model/V1RegisterWebhookRequest.md)|  | |

### Return type

[**\TheLogicStudio\GrailPay\Model\PostWebhook201Response**](../Model/PostWebhook201Response.md)

### Authorization

No authorization required

### HTTP request headers

- **Content-Type**: `application/json`
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `putBankAccountSwitchDefault()`

```php
putBankAccountSwitchDefault($user_uuid, $v1_switch_bank_account_request): \TheLogicStudio\GrailPay\Model\PutBankAccountSwitchDefault200Response
```

Switch default bank account ( STABLE )

Switch default bank account

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');



$apiInstance = new TheLogicStudio\GrailPay\Api\StableApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client()
);
$user_uuid = 'user_uuid_example'; // string | UUID of the user
$v1_switch_bank_account_request = new \TheLogicStudio\GrailPay\Model\V1SwitchBankAccountRequest(); // \TheLogicStudio\GrailPay\Model\V1SwitchBankAccountRequest | Switch default bank account

try {
    $result = $apiInstance->putBankAccountSwitchDefault($user_uuid, $v1_switch_bank_account_request);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling StableApi->putBankAccountSwitchDefault: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **user_uuid** | **string**| UUID of the user | |
| **v1_switch_bank_account_request** | [**\TheLogicStudio\GrailPay\Model\V1SwitchBankAccountRequest**](../Model/V1SwitchBankAccountRequest.md)| Switch default bank account | [optional] |

### Return type

[**\TheLogicStudio\GrailPay\Model\PutBankAccountSwitchDefault200Response**](../Model/PutBankAccountSwitchDefault200Response.md)

### Authorization

No authorization required

### HTTP request headers

- **Content-Type**: `application/json`
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)
