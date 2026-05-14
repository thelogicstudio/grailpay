# TheLogicStudio\GrailPay\BankAccountsApi



All URIs are relative to https://api.grailpay.com, except if the operation defines another base path.

| Method | HTTP request | Description |
| ------------- | ------------- | ------------- |
| [**deleteBankAccountsByAggregatorTypeByAccountUuid()**](BankAccountsApi.md#deleteBankAccountsByAggregatorTypeByAccountUuid) | **DELETE** /3p/api/v2/bank-accounts/{aggregator_type}/{account_uuid} | Delete a bank account ( STABLE ) |
| [**getBankAccountByUserUuid()**](BankAccountsApi.md#getBankAccountByUserUuid) | **GET** /3p/api/v1/bank-account/{user_uuid} | Get bank account details ( STABLE ) |
| [**getBankAccounts()**](BankAccountsApi.md#getBankAccounts) | **GET** /api/v3/bank-accounts | Get All Bank Accounts ( STABLE ) |
| [**getBankAccountsByAggregatorTypeByAccountUuidHistory()**](BankAccountsApi.md#getBankAccountsByAggregatorTypeByAccountUuidHistory) | **GET** /3p/api/v2/bank-accounts/{aggregator_type}/{account_uuid}/history | Fetch the transaction history for a bank account. ( STABLE ) |
| [**getBankAccountsByUuid()**](BankAccountsApi.md#getBankAccountsByUuid) | **GET** /api/v3/bank-accounts/{uuid} | Get Bank Account ( STABLE ) |
| [**getBankAccountsByUuidBalance()**](BankAccountsApi.md#getBankAccountsByUuidBalance) | **GET** /api/v3/bank-accounts/{uuid}/balance | Get Bank Account Balance (STABLE) |
| [**getBankAccountsByUuidOwners()**](BankAccountsApi.md#getBankAccountsByUuidOwners) | **GET** /api/v3/bank-accounts/{uuid}/owners | Get Bank Account Owners ( STABLE ) |
| [**getUsersByUuidBankAccounts()**](BankAccountsApi.md#getUsersByUuidBankAccounts) | **GET** /3p/api/v2/users/{uuid}/bank-accounts | Get all bank accounts for a user ( STABLE ) |
| [**getUsersByUuidBankAccountsByAccountUuidBalance()**](BankAccountsApi.md#getUsersByUuidBankAccountsByAccountUuidBalance) | **GET** /3p/api/v2/users/{uuid}/bank-accounts/{account_uuid}/balance | Fetch the bank account balance ( STABLE ) |
| [**postBankAccountBalanceByUserUuid()**](BankAccountsApi.md#postBankAccountBalanceByUserUuid) | **POST** /3p/api/v1/bank-account/balance/{user_uuid} | Get balance approval ( STABLE ) |
| [**postBankAccountUser()**](BankAccountsApi.md#postBankAccountUser) | **POST** /3p/api/v1/bank-account/user | Get User Details by bank account ( STABLE ) |
| [**postBankAccountsValidate()**](BankAccountsApi.md#postBankAccountsValidate) | **POST** /api/v3/bank-accounts/validate | Validate a bank account&#39;s routing and account number. ( STABLE ) |
| [**postPeopleByUuidBankAccounts()**](BankAccountsApi.md#postPeopleByUuidBankAccounts) | **POST** /api/v3/people/{uuid}/bank-accounts | Add a new bank account to a person. ( STABLE ) |
| [**putBankAccountSwitchDefaultByUserUuid()**](BankAccountsApi.md#putBankAccountSwitchDefaultByUserUuid) | **PUT** /3p/api/v1/bank-account/switch/default/{user_uuid} | Switch default bank account ( STABLE ) |


## `deleteBankAccountsByAggregatorTypeByAccountUuid()`

```php
deleteBankAccountsByAggregatorTypeByAccountUuid($aggregator_type, $account_uuid): \TheLogicStudio\GrailPay\Model\DeleteBankAccountsByAggregatorTypeByAccountUuid200Response
```

Delete a bank account ( STABLE )

Deletes a bank account by its UUID and aggregator type.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (Token) authorization: ApiToken
$config = TheLogicStudio\GrailPay\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new TheLogicStudio\GrailPay\Api\BankAccountsApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$aggregator_type = 'aggregator_type_example'; // string | The type of the bank aggregator
$account_uuid = 'account_uuid_example'; // string | The UUID of the bank account

try {
    $result = $apiInstance->deleteBankAccountsByAggregatorTypeByAccountUuid($aggregator_type, $account_uuid);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling BankAccountsApi->deleteBankAccountsByAggregatorTypeByAccountUuid: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **aggregator_type** | **string**| The type of the bank aggregator | |
| **account_uuid** | **string**| The UUID of the bank account | |

### Return type

[**\TheLogicStudio\GrailPay\Model\DeleteBankAccountsByAggregatorTypeByAccountUuid200Response**](../Model/DeleteBankAccountsByAggregatorTypeByAccountUuid200Response.md)

### Authorization

[ApiToken](../../README.md#ApiToken)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `getBankAccountByUserUuid()`

```php
getBankAccountByUserUuid($user_uuid): \TheLogicStudio\GrailPay\Model\GetBankAccountByUserUuid200Response
```

Get bank account details ( STABLE )

Retrieve the bank account details for a specific user.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (Token) authorization: ApiToken
$config = TheLogicStudio\GrailPay\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new TheLogicStudio\GrailPay\Api\BankAccountsApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$user_uuid = 'user_uuid_example'; // string | UUID of the user

try {
    $result = $apiInstance->getBankAccountByUserUuid($user_uuid);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling BankAccountsApi->getBankAccountByUserUuid: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **user_uuid** | **string**| UUID of the user | |

### Return type

[**\TheLogicStudio\GrailPay\Model\GetBankAccountByUserUuid200Response**](../Model/GetBankAccountByUserUuid200Response.md)

### Authorization

[ApiToken](../../README.md#ApiToken)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `getBankAccounts()`

```php
getBankAccounts($filter_entity_uuid, $filter_account_type, $filter_is_default, $filter_provider, $filter_account_name, $sort, $page, $per_page): \TheLogicStudio\GrailPay\Model\GetBankAccounts200Response
```

Get All Bank Accounts ( STABLE )

This endpoint returns a paginated list of bank accounts for the provided entity UUID.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (Token) authorization: ApiToken
$config = TheLogicStudio\GrailPay\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new TheLogicStudio\GrailPay\Api\BankAccountsApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$filter_entity_uuid = 7c41f6a2-a4b9-4df8-9225-2c1b7312042e; // string | Filter by entity UUID
$filter_account_type = checking; // string | Filter by account type
$filter_is_default = true; // string | Filter by default account status
$filter_provider = bank_link; // string | Filter by provider
$filter_account_name = Primary Checking; // string | Filter by account name
$sort = -created_at; // string | Sort by field (created_at, account_name). Prefix with '-' for descending order
$page = 1; // int | Page number for pagination
$per_page = 15; // int | Number of records per page

try {
    $result = $apiInstance->getBankAccounts($filter_entity_uuid, $filter_account_type, $filter_is_default, $filter_provider, $filter_account_name, $sort, $page, $per_page);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling BankAccountsApi->getBankAccounts: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **filter_entity_uuid** | **string**| Filter by entity UUID | |
| **filter_account_type** | **string**| Filter by account type | [optional] |
| **filter_is_default** | **string**| Filter by default account status | [optional] |
| **filter_provider** | **string**| Filter by provider | [optional] |
| **filter_account_name** | **string**| Filter by account name | [optional] |
| **sort** | **string**| Sort by field (created_at, account_name). Prefix with &#39;-&#39; for descending order | [optional] |
| **page** | **int**| Page number for pagination | [optional] |
| **per_page** | **int**| Number of records per page | [optional] [default to 15] |

### Return type

[**\TheLogicStudio\GrailPay\Model\GetBankAccounts200Response**](../Model/GetBankAccounts200Response.md)

### Authorization

[ApiToken](../../README.md#ApiToken)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `getBankAccountsByAggregatorTypeByAccountUuidHistory()`

```php
getBankAccountsByAggregatorTypeByAccountUuidHistory($aggregator_type, $account_uuid): \TheLogicStudio\GrailPay\Model\GetBankAccountsByAggregatorTypeByAccountUuidHistory200Response
```

Fetch the transaction history for a bank account. ( STABLE )

Fetch a list of transactions for a bank account.  This currently only works with accounts linked through the Bank Link SDK.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (Token) authorization: ApiToken
$config = TheLogicStudio\GrailPay\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new TheLogicStudio\GrailPay\Api\BankAccountsApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$aggregator_type = 'aggregator_type_example'; // string | Bank Account Provider.  Possible Values: bank_link
$account_uuid = 'account_uuid_example'; // string | UUID of the bank account

try {
    $result = $apiInstance->getBankAccountsByAggregatorTypeByAccountUuidHistory($aggregator_type, $account_uuid);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling BankAccountsApi->getBankAccountsByAggregatorTypeByAccountUuidHistory: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **aggregator_type** | **string**| Bank Account Provider.  Possible Values: bank_link | |
| **account_uuid** | **string**| UUID of the bank account | |

### Return type

[**\TheLogicStudio\GrailPay\Model\GetBankAccountsByAggregatorTypeByAccountUuidHistory200Response**](../Model/GetBankAccountsByAggregatorTypeByAccountUuidHistory200Response.md)

### Authorization

[ApiToken](../../README.md#ApiToken)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `getBankAccountsByUuid()`

```php
getBankAccountsByUuid($uuid): \TheLogicStudio\GrailPay\Model\GetBankAccountsByUuid200Response
```

Get Bank Account ( STABLE )

This endpoint returns the details of a single bank account and its associated entity information.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (Token) authorization: ApiToken
$config = TheLogicStudio\GrailPay\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new TheLogicStudio\GrailPay\Api\BankAccountsApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$uuid = 9b97f121-a449-4b52-9f36-6c55f18394d6; // string | bank account UUID

try {
    $result = $apiInstance->getBankAccountsByUuid($uuid);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling BankAccountsApi->getBankAccountsByUuid: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **uuid** | **string**| bank account UUID | |

### Return type

[**\TheLogicStudio\GrailPay\Model\GetBankAccountsByUuid200Response**](../Model/GetBankAccountsByUuid200Response.md)

### Authorization

[ApiToken](../../README.md#ApiToken)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `getBankAccountsByUuidBalance()`

```php
getBankAccountsByUuidBalance($uuid): \TheLogicStudio\GrailPay\Model\GetBankAccountsByUuidBalance200Response
```

Get Bank Account Balance (STABLE)

This endpoint returns the current balance for a specific Quiltt-linked bank account.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (Token) authorization: ApiToken
$config = TheLogicStudio\GrailPay\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new TheLogicStudio\GrailPay\Api\BankAccountsApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$uuid = 9b97f121-a449-4b52-9f36-6c55f18394d6; // string | Bank account UUID

try {
    $result = $apiInstance->getBankAccountsByUuidBalance($uuid);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling BankAccountsApi->getBankAccountsByUuidBalance: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **uuid** | **string**| Bank account UUID | |

### Return type

[**\TheLogicStudio\GrailPay\Model\GetBankAccountsByUuidBalance200Response**](../Model/GetBankAccountsByUuidBalance200Response.md)

### Authorization

[ApiToken](../../README.md#ApiToken)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `getBankAccountsByUuidOwners()`

```php
getBankAccountsByUuidOwners($uuid): \TheLogicStudio\GrailPay\Model\GetBankAccountsByUuidOwners200Response
```

Get Bank Account Owners ( STABLE )

This endpoint returns the account owners of the bank account.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (Token) authorization: ApiToken
$config = TheLogicStudio\GrailPay\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new TheLogicStudio\GrailPay\Api\BankAccountsApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$uuid = 9b97f121-a449-4b52-9f36-6c55f18394d6; // string | bank account UUID

try {
    $result = $apiInstance->getBankAccountsByUuidOwners($uuid);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling BankAccountsApi->getBankAccountsByUuidOwners: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **uuid** | **string**| bank account UUID | |

### Return type

[**\TheLogicStudio\GrailPay\Model\GetBankAccountsByUuidOwners200Response**](../Model/GetBankAccountsByUuidOwners200Response.md)

### Authorization

[ApiToken](../../README.md#ApiToken)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `getUsersByUuidBankAccounts()`

```php
getUsersByUuidBankAccounts($uuid): \TheLogicStudio\GrailPay\Model\GetUsersByUuidBankAccounts200Response
```

Get all bank accounts for a user ( STABLE )

This API retrieves a list of all bank accounts associated with a business or person. The response includes details such as the account number, routing number, account holder's name, account type, and other relevant information.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (Token) authorization: ApiToken
$config = TheLogicStudio\GrailPay\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new TheLogicStudio\GrailPay\Api\BankAccountsApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$uuid = 'uuid_example'; // string | UUID of the user

try {
    $result = $apiInstance->getUsersByUuidBankAccounts($uuid);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling BankAccountsApi->getUsersByUuidBankAccounts: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **uuid** | **string**| UUID of the user | |

### Return type

[**\TheLogicStudio\GrailPay\Model\GetUsersByUuidBankAccounts200Response**](../Model/GetUsersByUuidBankAccounts200Response.md)

### Authorization

[ApiToken](../../README.md#ApiToken)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `getUsersByUuidBankAccountsByAccountUuidBalance()`

```php
getUsersByUuidBankAccountsByAccountUuidBalance($uuid, $account_uuid): \TheLogicStudio\GrailPay\Model\GetUsersByUuidBankAccountsByAccountUuidBalance200Response
```

Fetch the bank account balance ( STABLE )

Fetch the balance of a specific bank account for a user.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (Token) authorization: ApiToken
$config = TheLogicStudio\GrailPay\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new TheLogicStudio\GrailPay\Api\BankAccountsApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$uuid = 'uuid_example'; // string | UUID of the user
$account_uuid = 'account_uuid_example'; // string | UUID of the bank account

try {
    $result = $apiInstance->getUsersByUuidBankAccountsByAccountUuidBalance($uuid, $account_uuid);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling BankAccountsApi->getUsersByUuidBankAccountsByAccountUuidBalance: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **uuid** | **string**| UUID of the user | |
| **account_uuid** | **string**| UUID of the bank account | |

### Return type

[**\TheLogicStudio\GrailPay\Model\GetUsersByUuidBankAccountsByAccountUuidBalance200Response**](../Model/GetUsersByUuidBankAccountsByAccountUuidBalance200Response.md)

### Authorization

[ApiToken](../../README.md#ApiToken)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `postBankAccountBalanceByUserUuid()`

```php
postBankAccountBalanceByUserUuid($user_uuid, $v1_get_bank_account_balance_request): \TheLogicStudio\GrailPay\Model\PostBankAccountBalanceByUserUuid200Response
```

Get balance approval ( STABLE )

Retrieve the balance approval for a specific user.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (Token) authorization: ApiToken
$config = TheLogicStudio\GrailPay\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new TheLogicStudio\GrailPay\Api\BankAccountsApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$user_uuid = 'user_uuid_example'; // string | UUID of the user
$v1_get_bank_account_balance_request = new \TheLogicStudio\GrailPay\Model\V1GetBankAccountBalanceRequest(); // \TheLogicStudio\GrailPay\Model\V1GetBankAccountBalanceRequest

try {
    $result = $apiInstance->postBankAccountBalanceByUserUuid($user_uuid, $v1_get_bank_account_balance_request);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling BankAccountsApi->postBankAccountBalanceByUserUuid: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **user_uuid** | **string**| UUID of the user | |
| **v1_get_bank_account_balance_request** | [**\TheLogicStudio\GrailPay\Model\V1GetBankAccountBalanceRequest**](../Model/V1GetBankAccountBalanceRequest.md)|  | |

### Return type

[**\TheLogicStudio\GrailPay\Model\PostBankAccountBalanceByUserUuid200Response**](../Model/PostBankAccountBalanceByUserUuid200Response.md)

### Authorization

[ApiToken](../../README.md#ApiToken)

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


// Configure Bearer (Token) authorization: ApiToken
$config = TheLogicStudio\GrailPay\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new TheLogicStudio\GrailPay\Api\BankAccountsApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$post_bank_account_user_request = new \TheLogicStudio\GrailPay\Model\PostBankAccountUserRequest(); // \TheLogicStudio\GrailPay\Model\PostBankAccountUserRequest

try {
    $result = $apiInstance->postBankAccountUser($post_bank_account_user_request);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling BankAccountsApi->postBankAccountUser: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **post_bank_account_user_request** | [**\TheLogicStudio\GrailPay\Model\PostBankAccountUserRequest**](../Model/PostBankAccountUserRequest.md)|  | |

### Return type

[**\TheLogicStudio\GrailPay\Model\PostBankAccountUser200Response**](../Model/PostBankAccountUser200Response.md)

### Authorization

[ApiToken](../../README.md#ApiToken)

### HTTP request headers

- **Content-Type**: `application/json`
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `postBankAccountsValidate()`

```php
postBankAccountsValidate($post_bank_accounts_validate_request): \TheLogicStudio\GrailPay\Model\PostBankAccountsValidate200Response
```

Validate a bank account's routing and account number. ( STABLE )

This endpoint allows for validating a Bank Account's routing and account number using GrailPay's Account Intelligence system.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (Token) authorization: ApiToken
$config = TheLogicStudio\GrailPay\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new TheLogicStudio\GrailPay\Api\BankAccountsApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$post_bank_accounts_validate_request = new \TheLogicStudio\GrailPay\Model\PostBankAccountsValidateRequest(); // \TheLogicStudio\GrailPay\Model\PostBankAccountsValidateRequest

try {
    $result = $apiInstance->postBankAccountsValidate($post_bank_accounts_validate_request);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling BankAccountsApi->postBankAccountsValidate: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **post_bank_accounts_validate_request** | [**\TheLogicStudio\GrailPay\Model\PostBankAccountsValidateRequest**](../Model/PostBankAccountsValidateRequest.md)|  | |

### Return type

[**\TheLogicStudio\GrailPay\Model\PostBankAccountsValidate200Response**](../Model/PostBankAccountsValidate200Response.md)

### Authorization

[ApiToken](../../README.md#ApiToken)

### HTTP request headers

- **Content-Type**: `application/json`
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `postPeopleByUuidBankAccounts()`

```php
postPeopleByUuidBankAccounts($uuid, $post_people_by_uuid_bank_accounts_request): \TheLogicStudio\GrailPay\Model\PostPeopleByUuidBankAccounts200Response
```

Add a new bank account to a person. ( STABLE )

This endpoint allows for adding a new Bank Account to the GrailPay ACH API Ecosystem. The only item that is required is the Bank Account object. When including the bank account, you can pass either Plaid information or account and routing information. You should never pass both.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (Token) authorization: ApiToken
$config = TheLogicStudio\GrailPay\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new TheLogicStudio\GrailPay\Api\BankAccountsApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$uuid = 7c41f6a2-a4b9-4df8-9225-2c1b7312042e; // string | UUID of the person
$post_people_by_uuid_bank_accounts_request = new \TheLogicStudio\GrailPay\Model\PostPeopleByUuidBankAccountsRequest(); // \TheLogicStudio\GrailPay\Model\PostPeopleByUuidBankAccountsRequest

try {
    $result = $apiInstance->postPeopleByUuidBankAccounts($uuid, $post_people_by_uuid_bank_accounts_request);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling BankAccountsApi->postPeopleByUuidBankAccounts: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **uuid** | **string**| UUID of the person | |
| **post_people_by_uuid_bank_accounts_request** | [**\TheLogicStudio\GrailPay\Model\PostPeopleByUuidBankAccountsRequest**](../Model/PostPeopleByUuidBankAccountsRequest.md)|  | |

### Return type

[**\TheLogicStudio\GrailPay\Model\PostPeopleByUuidBankAccounts200Response**](../Model/PostPeopleByUuidBankAccounts200Response.md)

### Authorization

[ApiToken](../../README.md#ApiToken)

### HTTP request headers

- **Content-Type**: `application/json`
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `putBankAccountSwitchDefaultByUserUuid()`

```php
putBankAccountSwitchDefaultByUserUuid($user_uuid, $v1_switch_bank_account_request): \TheLogicStudio\GrailPay\Model\PutBankAccountSwitchDefaultByUserUuid200Response
```

Switch default bank account ( STABLE )

Switch default bank account

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (Token) authorization: ApiToken
$config = TheLogicStudio\GrailPay\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new TheLogicStudio\GrailPay\Api\BankAccountsApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$user_uuid = 'user_uuid_example'; // string | UUID of the user
$v1_switch_bank_account_request = new \TheLogicStudio\GrailPay\Model\V1SwitchBankAccountRequest(); // \TheLogicStudio\GrailPay\Model\V1SwitchBankAccountRequest | Switch default bank account

try {
    $result = $apiInstance->putBankAccountSwitchDefaultByUserUuid($user_uuid, $v1_switch_bank_account_request);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling BankAccountsApi->putBankAccountSwitchDefaultByUserUuid: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **user_uuid** | **string**| UUID of the user | |
| **v1_switch_bank_account_request** | [**\TheLogicStudio\GrailPay\Model\V1SwitchBankAccountRequest**](../Model/V1SwitchBankAccountRequest.md)| Switch default bank account | [optional] |

### Return type

[**\TheLogicStudio\GrailPay\Model\PutBankAccountSwitchDefaultByUserUuid200Response**](../Model/PutBankAccountSwitchDefaultByUserUuid200Response.md)

### Authorization

[ApiToken](../../README.md#ApiToken)

### HTTP request headers

- **Content-Type**: `application/json`
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)
