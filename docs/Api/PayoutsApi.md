# TheLogicStudio\GrailPay\PayoutsApi

API Endpoints used for fetching payout information.

All URIs are relative to https://api.grailpay.com, except if the operation defines another base path.

| Method | HTTP request | Description |
| ------------- | ------------- | ------------- |
| [**getPayouts()**](PayoutsApi.md#getPayouts) | **GET** /api/v3/payouts | Get All Payouts |
| [**getPayoutsByUuid()**](PayoutsApi.md#getPayoutsByUuid) | **GET** /api/v3/payouts/{uuid} | Get Payout |
| [**postPayoutsStandalone()**](PayoutsApi.md#postPayoutsStandalone) | **POST** /api/v3/payouts/standalone | Create a standalone payout |


## `getPayouts()`

```php
getPayouts($filter_uuid, $filter_status, $filter_ach_id, $filter_payout_type, $filter_r_code, $filter_vendor_id, $filter_transaction_uuid, $filter_start_date, $filter_end_date, $filter_amount, $filter_merchant_uuid, $filter_user_uuid, $sort, $page, $per_page): \TheLogicStudio\GrailPay\Model\GetPayouts200Response
```

Get All Payouts

This endpoint provides a paginated list of payouts visible to the authenticated user, including transaction-linked and standalone payouts, with filtering and sorting options. Pass filter[payout_type]=processor to list batch payouts.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (Token) authorization: ApiToken
$config = TheLogicStudio\GrailPay\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new TheLogicStudio\GrailPay\Api\PayoutsApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$filter_uuid = a1e52556-7b0e-40d1-a787-9af5df215a57; // string | Filter by payout UUID
$filter_status = PAYOUT_ACH_PENDING; // string | Filter by payout status
$filter_ach_id = ach_11n1jzd31sgr9xd; // string | Filter by ACH trace ID
$filter_payout_type = standalone; // string | Filter by payout type. Use processor to list batch payouts (processor users only). Omit to list regular payouts.
$filter_r_code = R01; // string | Filter by ACH return code
$filter_vendor_id = 1; // int | Filter by vendor ID (processor users only)
$filter_transaction_uuid = 3fa85f64-5717-4562-b3fc-2c963f66afa6; // string | Filter by related transaction UUID
$filter_start_date = Mon Jan 01 13:00:00 NZDT 2024; // \DateTime | Filter payouts created on or after this date (YYYY-MM-DD)
$filter_end_date = Tue Dec 31 13:00:00 NZDT 2024; // \DateTime | Filter payouts created on or before this date (YYYY-MM-DD)
$filter_amount = >=100; // string | Filter by amount in cents. Supports dynamic operators (e.g. filter[amount]=100, filter[amount]=>100, filter[amount]=<=500)
$filter_merchant_uuid = 6a8fc154-1a50-483b-a690-fd1dfaf9408b; // string | Filter by merchant UUID on related transactions (payee or payer) or the payout recipient merchant
$filter_user_uuid = a182280a-9fe1-4f32-b055-4fd298c8c3ff; // string | Filter by payout recipient user UUID or recipient merchant UUID
$sort = -created_at; // string | Sort by field (created_at, amount). Prefix with '-' for descending order
$page = 1; // int | Page number for pagination
$per_page = 15; // int | Number of records per page

try {
    $result = $apiInstance->getPayouts($filter_uuid, $filter_status, $filter_ach_id, $filter_payout_type, $filter_r_code, $filter_vendor_id, $filter_transaction_uuid, $filter_start_date, $filter_end_date, $filter_amount, $filter_merchant_uuid, $filter_user_uuid, $sort, $page, $per_page);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling PayoutsApi->getPayouts: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **filter_uuid** | **string**| Filter by payout UUID | [optional] |
| **filter_status** | **string**| Filter by payout status | [optional] |
| **filter_ach_id** | **string**| Filter by ACH trace ID | [optional] |
| **filter_payout_type** | **string**| Filter by payout type. Use processor to list batch payouts (processor users only). Omit to list regular payouts. | [optional] |
| **filter_r_code** | **string**| Filter by ACH return code | [optional] |
| **filter_vendor_id** | **int**| Filter by vendor ID (processor users only) | [optional] |
| **filter_transaction_uuid** | **string**| Filter by related transaction UUID | [optional] |
| **filter_start_date** | **\DateTime**| Filter payouts created on or after this date (YYYY-MM-DD) | [optional] |
| **filter_end_date** | **\DateTime**| Filter payouts created on or before this date (YYYY-MM-DD) | [optional] |
| **filter_amount** | **string**| Filter by amount in cents. Supports dynamic operators (e.g. filter[amount]&#x3D;100, filter[amount]&#x3D;&gt;100, filter[amount]&#x3D;&lt;&#x3D;500) | [optional] |
| **filter_merchant_uuid** | **string**| Filter by merchant UUID on related transactions (payee or payer) or the payout recipient merchant | [optional] |
| **filter_user_uuid** | **string**| Filter by payout recipient user UUID or recipient merchant UUID | [optional] |
| **sort** | **string**| Sort by field (created_at, amount). Prefix with &#39;-&#39; for descending order | [optional] |
| **page** | **int**| Page number for pagination | [optional] |
| **per_page** | **int**| Number of records per page | [optional] [default to 15] |

### Return type

[**\TheLogicStudio\GrailPay\Model\GetPayouts200Response**](../Model/GetPayouts200Response.md)

### Authorization

[ApiToken](../../README.md#ApiToken)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `getPayoutsByUuid()`

```php
getPayoutsByUuid($uuid): \TheLogicStudio\GrailPay\Model\GetPayoutsByUuid200Response
```

Get Payout

This endpoint returns the details of a single payout (regular or batch). Regular and batch payouts return a payout + relations envelope. Soft-deleted bank accounts are included when present.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (Token) authorization: ApiToken
$config = TheLogicStudio\GrailPay\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new TheLogicStudio\GrailPay\Api\PayoutsApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$uuid = a1e52556-7b0e-40d1-a787-9af5df215a57; // string | Payout UUID

try {
    $result = $apiInstance->getPayoutsByUuid($uuid);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling PayoutsApi->getPayoutsByUuid: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **uuid** | **string**| Payout UUID | |

### Return type

[**\TheLogicStudio\GrailPay\Model\GetPayoutsByUuid200Response**](../Model/GetPayoutsByUuid200Response.md)

### Authorization

[ApiToken](../../README.md#ApiToken)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `postPayoutsStandalone()`

```php
postPayoutsStandalone($post_payouts_standalone_request): \TheLogicStudio\GrailPay\Model\PostPayoutsStandalone201Response
```

Create a standalone payout

Creates a vendor standalone payout for an entity. Requires the vendor to have standalone payouts enabled and a pre-funded FBO account configured. Supports idempotency via Idempotency-Key header.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (Token) authorization: ApiToken
$config = TheLogicStudio\GrailPay\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new TheLogicStudio\GrailPay\Api\PayoutsApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$post_payouts_standalone_request = new \TheLogicStudio\GrailPay\Model\PostPayoutsStandaloneRequest(); // \TheLogicStudio\GrailPay\Model\PostPayoutsStandaloneRequest | Standalone payout creation payload.

try {
    $result = $apiInstance->postPayoutsStandalone($post_payouts_standalone_request);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling PayoutsApi->postPayoutsStandalone: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **post_payouts_standalone_request** | [**\TheLogicStudio\GrailPay\Model\PostPayoutsStandaloneRequest**](../Model/PostPayoutsStandaloneRequest.md)| Standalone payout creation payload. | |

### Return type

[**\TheLogicStudio\GrailPay\Model\PostPayoutsStandalone201Response**](../Model/PostPayoutsStandalone201Response.md)

### Authorization

[ApiToken](../../README.md#ApiToken)

### HTTP request headers

- **Content-Type**: `application/json`
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)
