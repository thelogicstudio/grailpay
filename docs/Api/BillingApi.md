# TheLogicStudio\GrailPay\BillingApi

API Endpoints used for retrieving billing information.

All URIs are relative to https://api.grailpay.com, except if the operation defines another base path.

| Method | HTTP request | Description |
| ------------- | ------------- | ------------- |
| [**getMerchantsBilling()**](BillingApi.md#getMerchantsBilling) | **GET** /3p/api/v2/merchants/{uuid}/billing | Get Billing by Merchant User UUID ( STABLE ) |


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



$apiInstance = new TheLogicStudio\GrailPay\Api\BillingApi(
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
    echo 'Exception when calling BillingApi->getMerchantsBilling: ', $e->getMessage(), PHP_EOL;
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
