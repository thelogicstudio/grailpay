# TheLogicStudio\GrailPay\ReversePayoutsApi



All URIs are relative to https://api.grailpay.com, except if the operation defines another base path.

| Method | HTTP request | Description |
| ------------- | ------------- | ------------- |
| [**getReversePayouts()**](ReversePayoutsApi.md#getReversePayouts) | **GET** /api/v3/reverse-payouts | Get All Reverse Payouts |
| [**getReversePayoutsByUuid()**](ReversePayoutsApi.md#getReversePayoutsByUuid) | **GET** /api/v3/reverse-payouts/{uuid} | Get Reverse Payout |


## `getReversePayouts()`

```php
getReversePayouts($filter_uuid, $filter_status, $filter_r_code, $filter_transaction_uuid, $filter_start_date, $filter_end_date, $filter_amount, $sort, $page, $per_page): \TheLogicStudio\GrailPay\Model\GetReversePayouts200Response
```

Get All Reverse Payouts

This endpoint provides a paginated list of reverse payouts visible to the authenticated user, with filtering and sorting options.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (Token) authorization: ApiToken
$config = TheLogicStudio\GrailPay\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new TheLogicStudio\GrailPay\Api\ReversePayoutsApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$filter_uuid = 6b52f7b3-b5ca-5ef9-a336-3d2c8423153f; // string | Filter by reverse payout UUID
$filter_status = REVERSE_PAYOUT_ACH_PENDING; // string | Filter by reverse payout status
$filter_r_code = R01; // string | Filter by ACH return code
$filter_transaction_uuid = 3fa85f64-5717-4562-b3fc-2c963f66afa6; // string | Filter by the associated transaction UUID
$filter_start_date = Mon Jan 01 13:00:00 NZDT 2024; // \DateTime | Filter reverse payouts created on or after this date (YYYY-MM-DD)
$filter_end_date = Tue Dec 31 13:00:00 NZDT 2024; // \DateTime | Filter reverse payouts created on or before this date (YYYY-MM-DD)
$filter_amount = >=100; // string | Filter by amount in cents. Supports dynamic operators (e.g. filter[amount]=100, filter[amount]=>100, filter[amount]=<=500)
$sort = -created_at; // string | Sort by field (created_at, amount). Prefix with '-' for descending order
$page = 1; // int | Page number for pagination
$per_page = 15; // int | Number of records per page

try {
    $result = $apiInstance->getReversePayouts($filter_uuid, $filter_status, $filter_r_code, $filter_transaction_uuid, $filter_start_date, $filter_end_date, $filter_amount, $sort, $page, $per_page);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling ReversePayoutsApi->getReversePayouts: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **filter_uuid** | **string**| Filter by reverse payout UUID | [optional] |
| **filter_status** | **string**| Filter by reverse payout status | [optional] |
| **filter_r_code** | **string**| Filter by ACH return code | [optional] |
| **filter_transaction_uuid** | **string**| Filter by the associated transaction UUID | [optional] |
| **filter_start_date** | **\DateTime**| Filter reverse payouts created on or after this date (YYYY-MM-DD) | [optional] |
| **filter_end_date** | **\DateTime**| Filter reverse payouts created on or before this date (YYYY-MM-DD) | [optional] |
| **filter_amount** | **string**| Filter by amount in cents. Supports dynamic operators (e.g. filter[amount]&#x3D;100, filter[amount]&#x3D;&gt;100, filter[amount]&#x3D;&lt;&#x3D;500) | [optional] |
| **sort** | **string**| Sort by field (created_at, amount). Prefix with &#39;-&#39; for descending order | [optional] |
| **page** | **int**| Page number for pagination | [optional] |
| **per_page** | **int**| Number of records per page | [optional] [default to 15] |

### Return type

[**\TheLogicStudio\GrailPay\Model\GetReversePayouts200Response**](../Model/GetReversePayouts200Response.md)

### Authorization

[ApiToken](../../README.md#ApiToken)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `getReversePayoutsByUuid()`

```php
getReversePayoutsByUuid($uuid): \TheLogicStudio\GrailPay\Model\GetReversePayoutsByUuid200Response
```

Get Reverse Payout

This endpoint returns the details of a single reverse payout along with its associated transaction and payout. A reverse payout credits the original payer and always relates to exactly one transaction. Payout is null when the reverse payout was created before a payout existed.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (Token) authorization: ApiToken
$config = TheLogicStudio\GrailPay\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new TheLogicStudio\GrailPay\Api\ReversePayoutsApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$uuid = 6b52f7b3-b5ca-5ef9-a336-3d2c8423153f; // string | Reverse payout UUID

try {
    $result = $apiInstance->getReversePayoutsByUuid($uuid);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling ReversePayoutsApi->getReversePayoutsByUuid: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **uuid** | **string**| Reverse payout UUID | |

### Return type

[**\TheLogicStudio\GrailPay\Model\GetReversePayoutsByUuid200Response**](../Model/GetReversePayoutsByUuid200Response.md)

### Authorization

[ApiToken](../../README.md#ApiToken)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)
