# TheLogicStudio\GrailPay\AccountApi

API Endpoints used for retrieving the details of the authenticated vendor or processor.

All URIs are relative to https://api.grailpay.com, except if the operation defines another base path.

| Method | HTTP request | Description |
| ------------- | ------------- | ------------- |
| [**getMe()**](AccountApi.md#getMe) | **GET** /api/v3/me | Fetch Authenticated Account |


## `getMe()`

```php
getMe(): \TheLogicStudio\GrailPay\Model\GetMe200Response
```

Fetch Authenticated Account

Returns the entity the API token belongs to. Use it to confirm which account a token authenticates as, and to read that account's UUID for the endpoints that take one. `data.entity.type` is `vendor` or `processor`, and `uuid` is the UUID of that vendor or processor. The endpoint takes no parameters and always describes the caller, so it never returns another account's details. A vendor token must carry the `api.vendor.user.fetch` ability and a processor token `api.processor.user.fetch`; a token belonging to any other role is rejected.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (Token) authorization: ApiToken
$config = TheLogicStudio\GrailPay\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new TheLogicStudio\GrailPay\Api\AccountApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);

try {
    $result = $apiInstance->getMe();
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling AccountApi->getMe: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

This endpoint does not need any parameter.

### Return type

[**\TheLogicStudio\GrailPay\Model\GetMe200Response**](../Model/GetMe200Response.md)

### Authorization

[ApiToken](../../README.md#ApiToken)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)
