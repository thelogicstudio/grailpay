# TheLogicStudio\GrailPay\VendorsApi

API Endpoints used for managing vendor details, funding bank accounts, and the prefunded FBO account.

All URIs are relative to https://api.grailpay.com, except if the operation defines another base path.

| Method | HTTP request | Description |
| ------------- | ------------- | ------------- |
| [**deleteVendorsByUuidBankAccountsByBankAccountUuid()**](VendorsApi.md#deleteVendorsByUuidBankAccountsByBankAccountUuid) | **DELETE** /api/v3/vendors/{uuid}/bank-accounts/{bank_account_uuid} | Delete Vendor Bank Account |
| [**deleteVendorsByUuidFboFundingByFundingUuid()**](VendorsApi.md#deleteVendorsByUuidFboFundingByFundingUuid) | **DELETE** /api/v3/vendors/{uuid}/fbo/funding/{funding_uuid} | Cancel FBO Funding |
| [**getVendorsByUuid()**](VendorsApi.md#getVendorsByUuid) | **GET** /api/v3/vendors/{uuid} | Fetch Vendor Details |
| [**getVendorsByUuidBankAccounts()**](VendorsApi.md#getVendorsByUuidBankAccounts) | **GET** /api/v3/vendors/{uuid}/bank-accounts | List Vendor Bank Accounts |
| [**getVendorsByUuidFbo()**](VendorsApi.md#getVendorsByUuidFbo) | **GET** /api/v3/vendors/{uuid}/fbo | Fetch vendor prefunded FBO account details |
| [**postVendorsByUuidBankAccounts()**](VendorsApi.md#postVendorsByUuidBankAccounts) | **POST** /api/v3/vendors/{uuid}/bank-accounts | Add Vendor Bank Account |
| [**postVendorsByUuidFboFunding()**](VendorsApi.md#postVendorsByUuidFboFunding) | **POST** /api/v3/vendors/{uuid}/fbo/funding | Create FBO Funding |
| [**putVendorsByUuidBankAccountsByBankAccountUuidDefault()**](VendorsApi.md#putVendorsByUuidBankAccountsByBankAccountUuidDefault) | **PUT** /api/v3/vendors/{uuid}/bank-accounts/{bank_account_uuid}/default | Set Default Funding Bank Account |


## `deleteVendorsByUuidBankAccountsByBankAccountUuid()`

```php
deleteVendorsByUuidBankAccountsByBankAccountUuid($uuid, $bank_account_uuid): \TheLogicStudio\GrailPay\Model\DeleteBankAccountsByUuid200Response
```

Delete Vendor Bank Account

Deletes one of the authenticated vendor's funding bank accounts. The API token must belong to the vendor identified by {uuid}. A bank account that was used for a transfer, such as an FBO funding, within the last 30 days cannot be deleted. If the deleted account was the vendor's default funding bank account, the most recently added remaining funding bank account becomes the default; if none remain, the vendor has no default funding bank account.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (Token) authorization: ApiToken
$config = TheLogicStudio\GrailPay\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new TheLogicStudio\GrailPay\Api\VendorsApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$uuid = 7c41f6a2-a4b9-4df8-9225-2c1b7312042e; // string | UUID of the vendor
$bank_account_uuid = 0199c3e4-5a7b-7d21-8f3e-2b6c9d1a4e87; // string | UUID of one of the vendor's funding bank accounts

try {
    $result = $apiInstance->deleteVendorsByUuidBankAccountsByBankAccountUuid($uuid, $bank_account_uuid);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling VendorsApi->deleteVendorsByUuidBankAccountsByBankAccountUuid: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **uuid** | **string**| UUID of the vendor | |
| **bank_account_uuid** | **string**| UUID of one of the vendor&#39;s funding bank accounts | |

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

## `deleteVendorsByUuidFboFundingByFundingUuid()`

```php
deleteVendorsByUuidFboFundingByFundingUuid($uuid, $funding_uuid): \TheLogicStudio\GrailPay\Model\DeleteVendorsByUuidFboFundingByFundingUuid200Response
```

Cancel FBO Funding

Cancels a pending FBO funding created with `POST /api/v3/vendors/{uuid}/fbo/funding`. The API token must belong to the vendor identified by {uuid}. A funding can be canceled only while its ACH has not been processed, sent or settled; if it has already been submitted to the bank, it is canceled with the bank first. On success the response is HTTP 200 with the standard envelope, and an `fbo.funding_canceled` webhook event is emitted.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (Token) authorization: ApiToken
$config = TheLogicStudio\GrailPay\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new TheLogicStudio\GrailPay\Api\VendorsApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$uuid = 7c41f6a2-a4b9-4df8-9225-2c1b7312042e; // string | UUID of the vendor
$funding_uuid = 0199c3f0-2d4e-7a1b-9c6f-8e3d5b7a1f24; // string | UUID of the FBO funding, as returned when it was created

try {
    $result = $apiInstance->deleteVendorsByUuidFboFundingByFundingUuid($uuid, $funding_uuid);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling VendorsApi->deleteVendorsByUuidFboFundingByFundingUuid: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **uuid** | **string**| UUID of the vendor | |
| **funding_uuid** | **string**| UUID of the FBO funding, as returned when it was created | |

### Return type

[**\TheLogicStudio\GrailPay\Model\DeleteVendorsByUuidFboFundingByFundingUuid200Response**](../Model/DeleteVendorsByUuidFboFundingByFundingUuid200Response.md)

### Authorization

[ApiToken](../../README.md#ApiToken)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `getVendorsByUuid()`

```php
getVendorsByUuid($uuid): \TheLogicStudio\GrailPay\Model\GetVendorsByUuid200Response
```

Fetch Vendor Details

Returns the details of a vendor: its name, its funding bank accounts, and whether a prefunded FBO account is enabled for it. Readable either by the vendor itself or by the processor that owns it, so the API token must belong to the vendor identified by {uuid} or to its owning processor. `bank_accounts` holds the same funding bank accounts returned by `GET /api/v3/vendors/{uuid}/bank-accounts`, with account numbers masked except for the last four digits, and is an empty array when the vendor has none. `fbo_account.enabled` reports whether a prefunded FBO account is configured; when it is true, `GET /api/v3/vendors/{uuid}/fbo` returns that account's details and balance, but that endpoint is vendor-only, so an owning processor cannot call it with its own token.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (Token) authorization: ApiToken
$config = TheLogicStudio\GrailPay\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new TheLogicStudio\GrailPay\Api\VendorsApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$uuid = 7c41f6a2-a4b9-4df8-9225-2c1b7312042e; // string | UUID of the vendor

try {
    $result = $apiInstance->getVendorsByUuid($uuid);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling VendorsApi->getVendorsByUuid: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **uuid** | **string**| UUID of the vendor | |

### Return type

[**\TheLogicStudio\GrailPay\Model\GetVendorsByUuid200Response**](../Model/GetVendorsByUuid200Response.md)

### Authorization

[ApiToken](../../README.md#ApiToken)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `getVendorsByUuidBankAccounts()`

```php
getVendorsByUuidBankAccounts($uuid): \TheLogicStudio\GrailPay\Model\GetVendorsByUuidBankAccounts200Response
```

List Vendor Bank Accounts

Returns all funding bank accounts of the authenticated vendor, newest first. Funding bank accounts are the accounts debited by `POST /api/v3/vendors/{uuid}/fbo/funding`. The API token must belong to the vendor identified by {uuid}. The list is not paginated, and deleted bank accounts are not included. Account numbers are masked except for the last four digits.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (Token) authorization: ApiToken
$config = TheLogicStudio\GrailPay\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new TheLogicStudio\GrailPay\Api\VendorsApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$uuid = 7c41f6a2-a4b9-4df8-9225-2c1b7312042e; // string | UUID of the vendor

try {
    $result = $apiInstance->getVendorsByUuidBankAccounts($uuid);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling VendorsApi->getVendorsByUuidBankAccounts: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **uuid** | **string**| UUID of the vendor | |

### Return type

[**\TheLogicStudio\GrailPay\Model\GetVendorsByUuidBankAccounts200Response**](../Model/GetVendorsByUuidBankAccounts200Response.md)

### Authorization

[ApiToken](../../README.md#ApiToken)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `getVendorsByUuidFbo()`

```php
getVendorsByUuidFbo($uuid): \TheLogicStudio\GrailPay\Model\GetVendorsByUuidFbo200Response
```

Fetch vendor prefunded FBO account details

Returns live account details and available balance for the authenticated vendor's prefunded FBO account. This endpoint is vendor-only and requires the API token to belong to the vendor identified by {uuid}. Account and routing numbers are returned unmasked because the vendor is viewing their own FBO account.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (Token) authorization: ApiToken
$config = TheLogicStudio\GrailPay\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new TheLogicStudio\GrailPay\Api\VendorsApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$uuid = 7c41f6a2-a4b9-4df8-9225-2c1b7312042e; // string | UUID of the vendor

try {
    $result = $apiInstance->getVendorsByUuidFbo($uuid);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling VendorsApi->getVendorsByUuidFbo: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **uuid** | **string**| UUID of the vendor | |

### Return type

[**\TheLogicStudio\GrailPay\Model\GetVendorsByUuidFbo200Response**](../Model/GetVendorsByUuidFbo200Response.md)

### Authorization

[ApiToken](../../README.md#ApiToken)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `postVendorsByUuidBankAccounts()`

```php
postVendorsByUuidBankAccounts($uuid, $post_vendors_by_uuid_bank_accounts_request, $idempotency_key): \TheLogicStudio\GrailPay\Model\PostVendorsByUuidBankAccounts200Response
```

Add Vendor Bank Account

Adds a funding bank account to the authenticated vendor. Funding bank accounts are the accounts debited by `POST /api/v3/vendors/{uuid}/fbo/funding`. The API token must belong to the vendor identified by {uuid}. The routing number is verified and the account is registered with the bank before it is saved. If the vendor already has a funding bank account with the same account number, routing number and account type, that account is returned unchanged with HTTP 200 and the rest of the request, including `purposes.funding.default`, is not applied. The vendor's first funding bank account becomes its default funding bank account automatically; later accounts become the default only when `purposes.funding.default` is true. `purposes.funding.enabled` must be true and `purposes.payout` must not be sent. Unknown body parameters are rejected. Supports idempotency via the `Idempotency-Key` header.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (Token) authorization: ApiToken
$config = TheLogicStudio\GrailPay\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new TheLogicStudio\GrailPay\Api\VendorsApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$uuid = 7c41f6a2-a4b9-4df8-9225-2c1b7312042e; // string | UUID of the vendor
$post_vendors_by_uuid_bank_accounts_request = new \TheLogicStudio\GrailPay\Model\PostVendorsByUuidBankAccountsRequest(); // \TheLogicStudio\GrailPay\Model\PostVendorsByUuidBankAccountsRequest
$idempotency_key = vendor-bank-account-idempotency-key-123; // string | Optional idempotency key. Replaying the same key with the same request body returns the original response; a conflicting body returns 409.

try {
    $result = $apiInstance->postVendorsByUuidBankAccounts($uuid, $post_vendors_by_uuid_bank_accounts_request, $idempotency_key);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling VendorsApi->postVendorsByUuidBankAccounts: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **uuid** | **string**| UUID of the vendor | |
| **post_vendors_by_uuid_bank_accounts_request** | [**\TheLogicStudio\GrailPay\Model\PostVendorsByUuidBankAccountsRequest**](../Model/PostVendorsByUuidBankAccountsRequest.md)|  | |
| **idempotency_key** | **string**| Optional idempotency key. Replaying the same key with the same request body returns the original response; a conflicting body returns 409. | [optional] |

### Return type

[**\TheLogicStudio\GrailPay\Model\PostVendorsByUuidBankAccounts200Response**](../Model/PostVendorsByUuidBankAccounts200Response.md)

### Authorization

[ApiToken](../../README.md#ApiToken)

### HTTP request headers

- **Content-Type**: `application/json`
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `postVendorsByUuidFboFunding()`

```php
postVendorsByUuidFboFunding($uuid, $post_vendors_by_uuid_fbo_funding_request, $idempotency_key): \TheLogicStudio\GrailPay\Model\PostVendorsByUuidFboFunding201Response
```

Create FBO Funding

Creates an FBO funding: a same-day ACH debit (SEC code CCD) of `amount` cents from one of the authenticated vendor's funding bank accounts into the vendor's prefunded FBO account. The API token must belong to the vendor identified by {uuid}. The ACH is queued and submitted to the bank asynchronously, so a 201 response means the funding was created, not that funds have moved; an `fbo.funding_created` webhook event is emitted, and the returned `uuid` can be used to cancel the funding while it is still pending. `source_account` is optional. Omit it to debit the vendor's default funding bank account. Send only `source_account.uuid` to debit one of the vendor's funding bank accounts. Or send `account_number`, `routing_number`, `account_type` and `account_name` (and optionally `default`) to debit an account given by its details: if the vendor already has a funding bank account with the same account number, routing number and account type it is used, otherwise the routing number is verified, the account is registered with the bank and added to the vendor's funding bank accounts. `uuid` cannot be combined with account details or `default`. A bank account used for a funding cannot be deleted for the next 30 days. Unknown body parameters are rejected. Supports idempotency via the `Idempotency-Key` header.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (Token) authorization: ApiToken
$config = TheLogicStudio\GrailPay\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new TheLogicStudio\GrailPay\Api\VendorsApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$uuid = 7c41f6a2-a4b9-4df8-9225-2c1b7312042e; // string | UUID of the vendor
$post_vendors_by_uuid_fbo_funding_request = new \TheLogicStudio\GrailPay\Model\PostVendorsByUuidFboFundingRequest(); // \TheLogicStudio\GrailPay\Model\PostVendorsByUuidFboFundingRequest
$idempotency_key = fbo-funding-idempotency-key-123; // string | Optional idempotency key. Replaying the same key with the same request body returns the original response; a conflicting body returns 409.

try {
    $result = $apiInstance->postVendorsByUuidFboFunding($uuid, $post_vendors_by_uuid_fbo_funding_request, $idempotency_key);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling VendorsApi->postVendorsByUuidFboFunding: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **uuid** | **string**| UUID of the vendor | |
| **post_vendors_by_uuid_fbo_funding_request** | [**\TheLogicStudio\GrailPay\Model\PostVendorsByUuidFboFundingRequest**](../Model/PostVendorsByUuidFboFundingRequest.md)|  | |
| **idempotency_key** | **string**| Optional idempotency key. Replaying the same key with the same request body returns the original response; a conflicting body returns 409. | [optional] |

### Return type

[**\TheLogicStudio\GrailPay\Model\PostVendorsByUuidFboFunding201Response**](../Model/PostVendorsByUuidFboFunding201Response.md)

### Authorization

[ApiToken](../../README.md#ApiToken)

### HTTP request headers

- **Content-Type**: `application/json`
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `putVendorsByUuidBankAccountsByBankAccountUuidDefault()`

```php
putVendorsByUuidBankAccountsByBankAccountUuidDefault($uuid, $bank_account_uuid, $idempotency_key): \TheLogicStudio\GrailPay\Model\PutVendorsByUuidBankAccountsByBankAccountUuidDefault200Response
```

Set Default Funding Bank Account

Makes one of the authenticated vendor's funding bank accounts its default funding bank account, which `POST /api/v3/vendors/{uuid}/fbo/funding` debits when no `source_account` is given. The API token must belong to the vendor identified by {uuid}. Setting the account that is already the default succeeds without changes. The endpoint takes no body parameters; any parameter sent is rejected. Supports idempotency via the `Idempotency-Key` header.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (Token) authorization: ApiToken
$config = TheLogicStudio\GrailPay\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new TheLogicStudio\GrailPay\Api\VendorsApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$uuid = 7c41f6a2-a4b9-4df8-9225-2c1b7312042e; // string | UUID of the vendor
$bank_account_uuid = 0199c3e4-5a7b-7d21-8f3e-2b6c9d1a4e87; // string | UUID of one of the vendor's funding bank accounts
$idempotency_key = vendor-default-bank-account-idempotency-key-123; // string | Optional idempotency key. Replaying the same key with the same request returns the original response; a conflicting request returns 409.

try {
    $result = $apiInstance->putVendorsByUuidBankAccountsByBankAccountUuidDefault($uuid, $bank_account_uuid, $idempotency_key);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling VendorsApi->putVendorsByUuidBankAccountsByBankAccountUuidDefault: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **uuid** | **string**| UUID of the vendor | |
| **bank_account_uuid** | **string**| UUID of one of the vendor&#39;s funding bank accounts | |
| **idempotency_key** | **string**| Optional idempotency key. Replaying the same key with the same request returns the original response; a conflicting request returns 409. | [optional] |

### Return type

[**\TheLogicStudio\GrailPay\Model\PutVendorsByUuidBankAccountsByBankAccountUuidDefault200Response**](../Model/PutVendorsByUuidBankAccountsByBankAccountUuidDefault200Response.md)

### Authorization

[ApiToken](../../README.md#ApiToken)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)
