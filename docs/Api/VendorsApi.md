# TheLogicStudio\GrailPay\VendorsApi

Vendors

All URIs are relative to https://api.grailpay.com, except if the operation defines another base path.

| Method | HTTP request | Description |
| ------------- | ------------- | ------------- |
| [**getVendorsByUuidFbo()**](VendorsApi.md#getVendorsByUuidFbo) | **GET** /api/v3/vendors/{uuid}/fbo | Fetch vendor prefunded FBO account details ( STABLE ) |


## `getVendorsByUuidFbo()`

```php
getVendorsByUuidFbo($uuid): \TheLogicStudio\GrailPay\Model\GetVendorsByUuidFbo200Response
```

Fetch vendor prefunded FBO account details ( STABLE )

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
