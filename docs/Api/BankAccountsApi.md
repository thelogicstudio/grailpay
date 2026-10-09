# TheLogicStudio\GrailPay\BankAccountsApi



All URIs are relative to https://api.grailpay.com, except if the operation defines another base path.

| Method | HTTP request | Description |
| ------------- | ------------- | ------------- |
| [**deleteBankAccountsByUuid()**](BankAccountsApi.md#deleteBankAccountsByUuid) | **DELETE** /api/v3/bank-accounts/{uuid} | Delete a bank account. |
| [**getBankAccounts()**](BankAccountsApi.md#getBankAccounts) | **GET** /api/v3/bank-accounts | List bank accounts for an entity. |
| [**getBankAccountsByUuid()**](BankAccountsApi.md#getBankAccountsByUuid) | **GET** /api/v3/bank-accounts/{uuid} | Show a bank account. |
| [**getBankAccountsByUuidBalance()**](BankAccountsApi.md#getBankAccountsByUuidBalance) | **GET** /api/v3/bank-accounts/{uuid}/balance | Fetch a bank account balance. |
| [**getBankAccountsByUuidHistory()**](BankAccountsApi.md#getBankAccountsByUuidHistory) | **GET** /api/v3/bank-accounts/{uuid}/history | Fetch bank account transaction history. |
| [**getBankAccountsByUuidOwners()**](BankAccountsApi.md#getBankAccountsByUuidOwners) | **GET** /api/v3/bank-accounts/{uuid}/owners | Get Bank Account Owners |
| [**postBankAccounts()**](BankAccountsApi.md#postBankAccounts) | **POST** /api/v3/bank-accounts | Add a bank account to an entity. |
| [**postBankAccountsValidate()**](BankAccountsApi.md#postBankAccountsValidate) | **POST** /api/v3/bank-accounts/validate | Validate a bank account&#39;s routing and account number. |
| [**postPeopleByUuidBankAccounts()**](BankAccountsApi.md#postPeopleByUuidBankAccounts) | **POST** /api/v3/people/{uuid}/bank-accounts | Add a new bank account to a person. |
| [**putBankAccountsByUuidDefault()**](BankAccountsApi.md#putBankAccountsByUuidDefault) | **PUT** /api/v3/bank-accounts/{uuid}/default | Switch the default bank account. |


## `deleteBankAccountsByUuid()`

```php
deleteBankAccountsByUuid($uuid): \TheLogicStudio\GrailPay\Model\DeleteBankAccountsByUuid200Response
```

Delete a bank account.

This endpoint deletes a bank account by its UUID. The bank account must be eligible for deletion (no recent transaction activity within the configured period).

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
$uuid = 7c41f6a2-a4b9-4df8-9225-2c1b7312042e; // string | UUID of the bank account to delete

try {
    $result = $apiInstance->deleteBankAccountsByUuid($uuid);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling BankAccountsApi->deleteBankAccountsByUuid: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **uuid** | **string**| UUID of the bank account to delete | |

### Return type

[**\TheLogicStudio\GrailPay\Model\DeleteBankAccountsByUuid200Response**](../Model/DeleteBankAccountsByUuid200Response.md)

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
getBankAccounts($filter_entity_uuid, $filter_account_type, $filter_is_default, $filter_provider, $filter_account_name, $sort, $per_page, $page): \TheLogicStudio\GrailPay\Model\GetBankAccounts200Response
```

List bank accounts for an entity.

This endpoint retrieves a paginated list of bank accounts for a given entity. Supports filtering by account type, default status, provider, and account name. Supports sorting by created_at and account_name.

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
$filter_entity_uuid = 7c41f6a2-a4b9-4df8-9225-2c1b7312042e; // string | UUID of the entity (person or business) to list bank accounts for
$filter_account_type = checking; // string | Filter by account type
$filter_is_default = true; // string | Filter by default account status
$filter_provider = manual; // string | Filter by provider type
$filter_account_name = Checking; // string | Filter by account name (partial match)
$sort = -created_at; // string | Sort field. Prefix with - for descending order.
$per_page = 15; // int | Number of records per page
$page = 1; // int | Page number

try {
    $result = $apiInstance->getBankAccounts($filter_entity_uuid, $filter_account_type, $filter_is_default, $filter_provider, $filter_account_name, $sort, $per_page, $page);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling BankAccountsApi->getBankAccounts: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **filter_entity_uuid** | **string**| UUID of the entity (person or business) to list bank accounts for | |
| **filter_account_type** | **string**| Filter by account type | [optional] |
| **filter_is_default** | **string**| Filter by default account status | [optional] |
| **filter_provider** | **string**| Filter by provider type | [optional] |
| **filter_account_name** | **string**| Filter by account name (partial match) | [optional] |
| **sort** | **string**| Sort field. Prefix with - for descending order. | [optional] |
| **per_page** | **int**| Number of records per page | [optional] |
| **page** | **int**| Page number | [optional] |

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

## `getBankAccountsByUuid()`

```php
getBankAccountsByUuid($uuid): \TheLogicStudio\GrailPay\Model\GetBankAccountsByUuid200Response
```

Show a bank account.

This endpoint retrieves the details of a specific bank account by its UUID, including the associated entity information.

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
$uuid = 7c41f6a2-a4b9-4df8-9225-2c1b7312042e; // string | UUID of the bank account

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
| **uuid** | **string**| UUID of the bank account | |

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

Fetch a bank account balance.

This endpoint fetches the current balance of a bank account. Only available for bank-link (Quiltt/MoneyKit) provider accounts.

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
$uuid = 7c41f6a2-a4b9-4df8-9225-2c1b7312042e; // string | UUID of the bank account

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
| **uuid** | **string**| UUID of the bank account | |

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

## `getBankAccountsByUuidHistory()`

```php
getBankAccountsByUuidHistory($uuid, $per_page, $start_date, $end_date, $page, $cursor): \TheLogicStudio\GrailPay\Model\QuilttProviderResponse
```

Fetch bank account transaction history.

This endpoint fetches the transaction history for a bank account. Supports two providers: **Quiltt** (cursor-based pagination with advanced filtering) and **MoneyKit** (page-based pagination with basic date filtering). The available parameters and response format depend on the bank account's provider.

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
$uuid = 7c41f6a2-a4b9-4df8-9225-2c1b7312042e; // string | UUID of the bank account. (Both providers)
$per_page = 15; // int | Number of records per page. Used as page size for MoneyKit and as first/page size for Quiltt cursor-based pagination. (Both providers)
$start_date = Mon Jan 01 13:00:00 NZDT 2024; // \DateTime | Start date filter (Y-m-d format). Must be before or equal to end_date. (Both providers)
$end_date = Tue Dec 31 13:00:00 NZDT 2024; // \DateTime | End date filter (Y-m-d format). Must be after or equal to start_date. (Both providers)
$page = 1; // int | Page number for page-based pagination. (MoneyKit only)
$cursor = 'cursor_example'; // string | Cursor for cursor-based pagination. (Quiltt only)

try {
    $result = $apiInstance->getBankAccountsByUuidHistory($uuid, $per_page, $start_date, $end_date, $page, $cursor);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling BankAccountsApi->getBankAccountsByUuidHistory: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **uuid** | **string**| UUID of the bank account. (Both providers) | |
| **per_page** | **int**| Number of records per page. Used as page size for MoneyKit and as first/page size for Quiltt cursor-based pagination. (Both providers) | [optional] |
| **start_date** | **\DateTime**| Start date filter (Y-m-d format). Must be before or equal to end_date. (Both providers) | [optional] |
| **end_date** | **\DateTime**| End date filter (Y-m-d format). Must be after or equal to start_date. (Both providers) | [optional] |
| **page** | **int**| Page number for page-based pagination. (MoneyKit only) | [optional] |
| **cursor** | **string**| Cursor for cursor-based pagination. (Quiltt only) | [optional] |

### Return type

[**\TheLogicStudio\GrailPay\Model\QuilttProviderResponse**](../Model/QuilttProviderResponse.md)

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

Get Bank Account Owners

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

## `postBankAccounts()`

```php
postBankAccounts($post_bank_accounts_request): \TheLogicStudio\GrailPay\Model\PostBankAccounts200Response
```

Add a bank account to an entity.

This endpoint allows for adding a new Bank Account to an entity (person or business) using their entity UUID. You can pass either Plaid information or account and routing information. You should never pass both.

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
$post_bank_accounts_request = new \TheLogicStudio\GrailPay\Model\PostBankAccountsRequest(); // \TheLogicStudio\GrailPay\Model\PostBankAccountsRequest

try {
    $result = $apiInstance->postBankAccounts($post_bank_accounts_request);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling BankAccountsApi->postBankAccounts: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **post_bank_accounts_request** | [**\TheLogicStudio\GrailPay\Model\PostBankAccountsRequest**](../Model/PostBankAccountsRequest.md)|  | |

### Return type

[**\TheLogicStudio\GrailPay\Model\PostBankAccounts200Response**](../Model/PostBankAccounts200Response.md)

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

Validate a bank account's routing and account number.

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

Add a new bank account to a person.

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

## `putBankAccountsByUuidDefault()`

```php
putBankAccountsByUuidDefault($uuid): \TheLogicStudio\GrailPay\Model\PutBankAccountsByUuidDefault200Response
```

Switch the default bank account.

This endpoint sets a bank account as the default bank account for the entity. The bank account must be in a connected state for Quiltt/MoneyKit providers, and the entity must be approved and not scheduled for deletion.

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
$uuid = 7c41f6a2-a4b9-4df8-9225-2c1b7312042e; // string | UUID of the bank account to set as default

try {
    $result = $apiInstance->putBankAccountsByUuidDefault($uuid);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling BankAccountsApi->putBankAccountsByUuidDefault: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **uuid** | **string**| UUID of the bank account to set as default | |

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
