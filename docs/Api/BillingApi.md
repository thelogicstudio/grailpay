# TheLogicStudio\GrailPay\BillingApi

API Endpoints used for retrieving billing information.

All URIs are relative to https://api.grailpay.com, except if the operation defines another base path.

| Method | HTTP request | Description |
| ------------- | ------------- | ------------- |
| [**getBillingItems()**](BillingApi.md#getBillingItems) | **GET** /api/v3/billing/items | Get Billing Items |
| [**getBillingSummary()**](BillingApi.md#getBillingSummary) | **GET** /api/v3/billing/summary | Get Billing Summary |


## `getBillingItems()`

```php
getBillingItems($filter_start_date, $filter_end_date, $filter_billable_event_name, $filter_entity_uuid, $filter_processor_mid, $sort, $page, $per_page): \TheLogicStudio\GrailPay\Model\GetBillingItems200Response
```

Get Billing Items

Returns a paginated list of individual billable events visible to the authenticated vendor or processor. Entity is resolved from the billing user (vendor-business merchant or vendor-person). Source comes from the billing eventable. When filter[start_date] or filter[end_date] is omitted, defaults are the first day of the current month and today.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (Token) authorization: ApiToken
$config = TheLogicStudio\GrailPay\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new TheLogicStudio\GrailPay\Api\BillingApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$filter_start_date = Tue Sep 01 12:00:00 NZST 2026; // \DateTime | Inclusive start date (YYYY-MM-DD). Defaults to the first day of the current month when omitted.
$filter_end_date = Fri Sep 18 12:00:00 NZST 2026; // \DateTime | Inclusive end date (YYYY-MM-DD). Defaults to today when omitted.
$filter_billable_event_name = new \TheLogicStudio\GrailPay\Model\\TheLogicStudio\GrailPay\Model\V3BillableEventName(); // \TheLogicStudio\GrailPay\Model\V3BillableEventName | Filter by billable event display name (e.g. Balance Check).
$filter_entity_uuid = 6a8fc154-1a50-483b-a690-fd1dfaf9408b; // string | Filter by billing user UUID or that user's merchant UUID.
$filter_processor_mid = 234234234; // string | Filter by processor MID on the billing user's merchant.
$sort = -created_at; // string | Sort by created_at or amount. Prefix with '-' for descending order.
$page = 1; // int | Page number for pagination
$per_page = 15; // int | Number of records per page

try {
    $result = $apiInstance->getBillingItems($filter_start_date, $filter_end_date, $filter_billable_event_name, $filter_entity_uuid, $filter_processor_mid, $sort, $page, $per_page);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling BillingApi->getBillingItems: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **filter_start_date** | **\DateTime**| Inclusive start date (YYYY-MM-DD). Defaults to the first day of the current month when omitted. | [optional] |
| **filter_end_date** | **\DateTime**| Inclusive end date (YYYY-MM-DD). Defaults to today when omitted. | [optional] |
| **filter_billable_event_name** | [**\TheLogicStudio\GrailPay\Model\V3BillableEventName**](../Model/.md)| Filter by billable event display name (e.g. Balance Check). | [optional] |
| **filter_entity_uuid** | **string**| Filter by billing user UUID or that user&#39;s merchant UUID. | [optional] |
| **filter_processor_mid** | **string**| Filter by processor MID on the billing user&#39;s merchant. | [optional] |
| **sort** | **string**| Sort by created_at or amount. Prefix with &#39;-&#39; for descending order. | [optional] |
| **page** | **int**| Page number for pagination | [optional] |
| **per_page** | **int**| Number of records per page | [optional] [default to 15] |

### Return type

[**\TheLogicStudio\GrailPay\Model\GetBillingItems200Response**](../Model/GetBillingItems200Response.md)

### Authorization

[ApiToken](../../README.md#ApiToken)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `getBillingSummary()`

```php
getBillingSummary($filter_start_date, $filter_end_date, $filter_billable_event_name, $filter_merchant_name, $filter_entity_uuid, $filter_processor_mid, $page, $per_page): \TheLogicStudio\GrailPay\Model\GetBillingSummary200Response
```

Get Billing Summary

Returns a paginated billing summary grouped by entity (merchant, business, or person). Entity is resolved from the billing user and optional merchant. Filters include entity_uuid (merchant UUID or user UUID), merchant_name, processor_mid, billable_event_name, and date range.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (Token) authorization: ApiToken
$config = TheLogicStudio\GrailPay\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new TheLogicStudio\GrailPay\Api\BillingApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$filter_start_date = Tue Sep 01 12:00:00 NZST 2026; // \DateTime | Inclusive start date (YYYY-MM-DD).
$filter_end_date = Fri Sep 18 12:00:00 NZST 2026; // \DateTime | Inclusive end date (YYYY-MM-DD).
$filter_billable_event_name = new \TheLogicStudio\GrailPay\Model\\TheLogicStudio\GrailPay\Model\V3BillableEventName(); // \TheLogicStudio\GrailPay\Model\V3BillableEventName | Filter by billable event display name (e.g. Balance Check).
$filter_merchant_name = Acme; // string | Partial match on merchant name.
$filter_entity_uuid = 6a8fc154-1a50-483b-a690-fd1dfaf9408b; // string | Filter by merchant UUID or billing user UUID.
$filter_processor_mid = 234234234; // string | Filter by processor MID on the merchant.
$page = 1; // int | Page number for pagination
$per_page = 15; // int | Number of records per page

try {
    $result = $apiInstance->getBillingSummary($filter_start_date, $filter_end_date, $filter_billable_event_name, $filter_merchant_name, $filter_entity_uuid, $filter_processor_mid, $page, $per_page);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling BillingApi->getBillingSummary: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **filter_start_date** | **\DateTime**| Inclusive start date (YYYY-MM-DD). | [optional] |
| **filter_end_date** | **\DateTime**| Inclusive end date (YYYY-MM-DD). | [optional] |
| **filter_billable_event_name** | [**\TheLogicStudio\GrailPay\Model\V3BillableEventName**](../Model/.md)| Filter by billable event display name (e.g. Balance Check). | [optional] |
| **filter_merchant_name** | **string**| Partial match on merchant name. | [optional] |
| **filter_entity_uuid** | **string**| Filter by merchant UUID or billing user UUID. | [optional] |
| **filter_processor_mid** | **string**| Filter by processor MID on the merchant. | [optional] |
| **page** | **int**| Page number for pagination | [optional] |
| **per_page** | **int**| Number of records per page | [optional] [default to 15] |

### Return type

[**\TheLogicStudio\GrailPay\Model\GetBillingSummary200Response**](../Model/GetBillingSummary200Response.md)

### Authorization

[ApiToken](../../README.md#ApiToken)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)
