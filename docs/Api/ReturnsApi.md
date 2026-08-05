# TheLogicStudio\GrailPay\ReturnsApi

API Endpoints used for retrieving ACH return information.

All URIs are relative to https://api.grailpay.com, except if the operation defines another base path.

| Method | HTTP request | Description |
| ------------- | ------------- | ------------- |
| [**getReturns()**](ReturnsApi.md#getReturns) | **GET** /api/v3/returns | Get All Returns ( STABLE ) |


## `getReturns()`

```php
getReturns($filter_leg, $filter_ach_return_code, $filter_ach_return_codes, $filter_amount, $filter_transaction_uuid, $filter_payout_uuid, $filter_clawback_uuid, $filter_reverse_payout_uuid, $filter_entity_uuid, $filter_vendor_id, $filter_bank_id, $filter_trace_id, $filter_start_date, $filter_end_date, $sort, $page, $per_page): \TheLogicStudio\GrailPay\Model\GetReturns200Response
```

Get All Returns ( STABLE )

This endpoint provides a paginated list of ACH returns visible to the authenticated user. Returns are sourced from capture (transaction) and payout legs, with filtering and sorting options.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (Token) authorization: ApiToken
$config = TheLogicStudio\GrailPay\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new TheLogicStudio\GrailPay\Api\ReturnsApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$filter_leg = new \TheLogicStudio\GrailPay\Model\\TheLogicStudio\GrailPay\Model\V3ReturnLegEnum(); // \TheLogicStudio\GrailPay\Model\V3ReturnLegEnum | Filter by return leg. When omitted, both capture and payout legs are included.
$filter_ach_return_code = R01; // string | Filter by a single ACH return code
$filter_ach_return_codes = R01,R02,R03; // string | Filter by multiple ACH return codes (comma-separated)
$filter_amount = >=12500; // string | Filter by amount in cents (e.g., 12500 = $125.00). Supports dynamic operators (e.g. filter[amount]=12500, filter[amount]=>10000, filter[amount]=<=50000)
$filter_transaction_uuid = 3fa85f64-5717-4562-b3fc-2c963f66afa6; // string | Filter by transaction UUID
$filter_payout_uuid = a1e52556-7b0e-40d1-a787-9af5df215a57; // string | Filter by payout UUID (payout or processor payout on capture leg)
$filter_clawback_uuid = 7c41f6a2-a4b9-4df8-9225-2c1b7312042e; // string | Filter by clawback UUID
$filter_reverse_payout_uuid = 6b52f7b3-b5ca-5ef9-a336-3d2c8423153f; // string | Filter by reverse payout UUID
$filter_entity_uuid = 019e0834-c96a-7d71-bb60-bda7b9a26d1a; // string | Filter by payor or payee person or merchant UUID
$filter_vendor_id = 1; // int | Filter by vendor ID (processor only)
$filter_bank_id = ach_11n4zxrp1twjebp; // string | Filter by bank identifier
$filter_trace_id = 2145642244586478; // string | Filter by ACH trace ID or bank identifier
$filter_start_date = Mon Jan 01 13:00:00 NZDT 2024; // \DateTime | Filter returns with ACH failure on or after this date (YYYY-MM-DD)
$filter_end_date = Tue Dec 31 13:00:00 NZDT 2024; // \DateTime | Filter returns with ACH failure on or before this date (YYYY-MM-DD)
$sort = -ach_failed_at; // string | Sort by field (ach_failed_at, amount). Prefix with '-' for descending order
$page = 1; // int | Page number for pagination
$per_page = 15; // int | Number of records per page

try {
    $result = $apiInstance->getReturns($filter_leg, $filter_ach_return_code, $filter_ach_return_codes, $filter_amount, $filter_transaction_uuid, $filter_payout_uuid, $filter_clawback_uuid, $filter_reverse_payout_uuid, $filter_entity_uuid, $filter_vendor_id, $filter_bank_id, $filter_trace_id, $filter_start_date, $filter_end_date, $sort, $page, $per_page);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling ReturnsApi->getReturns: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **filter_leg** | [**\TheLogicStudio\GrailPay\Model\V3ReturnLegEnum**](../Model/.md)| Filter by return leg. When omitted, both capture and payout legs are included. | [optional] |
| **filter_ach_return_code** | **string**| Filter by a single ACH return code | [optional] |
| **filter_ach_return_codes** | **string**| Filter by multiple ACH return codes (comma-separated) | [optional] |
| **filter_amount** | **string**| Filter by amount in cents (e.g., 12500 &#x3D; $125.00). Supports dynamic operators (e.g. filter[amount]&#x3D;12500, filter[amount]&#x3D;&gt;10000, filter[amount]&#x3D;&lt;&#x3D;50000) | [optional] |
| **filter_transaction_uuid** | **string**| Filter by transaction UUID | [optional] |
| **filter_payout_uuid** | **string**| Filter by payout UUID (payout or processor payout on capture leg) | [optional] |
| **filter_clawback_uuid** | **string**| Filter by clawback UUID | [optional] |
| **filter_reverse_payout_uuid** | **string**| Filter by reverse payout UUID | [optional] |
| **filter_entity_uuid** | **string**| Filter by payor or payee person or merchant UUID | [optional] |
| **filter_vendor_id** | **int**| Filter by vendor ID (processor only) | [optional] |
| **filter_bank_id** | **string**| Filter by bank identifier | [optional] |
| **filter_trace_id** | **string**| Filter by ACH trace ID or bank identifier | [optional] |
| **filter_start_date** | **\DateTime**| Filter returns with ACH failure on or after this date (YYYY-MM-DD) | [optional] |
| **filter_end_date** | **\DateTime**| Filter returns with ACH failure on or before this date (YYYY-MM-DD) | [optional] |
| **sort** | **string**| Sort by field (ach_failed_at, amount). Prefix with &#39;-&#39; for descending order | [optional] |
| **page** | **int**| Page number for pagination | [optional] |
| **per_page** | **int**| Number of records per page | [optional] [default to 15] |

### Return type

[**\TheLogicStudio\GrailPay\Model\GetReturns200Response**](../Model/GetReturns200Response.md)

### Authorization

[ApiToken](../../README.md#ApiToken)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)
