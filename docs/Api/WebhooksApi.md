# TheLogicStudio\GrailPay\WebhooksApi

API Endpoints used for registering and de-registering webhooks.

All URIs are relative to https://api.grailpay.com, except if the operation defines another base path.

| Method | HTTP request | Description |
| ------------- | ------------- | ------------- |
| [**deleteWebhook()**](WebhooksApi.md#deleteWebhook) | **DELETE** /3p/api/v1/webhook | De-register Webhook ( STABLE ) |
| [**getWebhook()**](WebhooksApi.md#getWebhook) | **GET** /3p/api/v1/webhook | Get registered webhooks ( STABLE ) |
| [**postWebhook()**](WebhooksApi.md#postWebhook) | **POST** /3p/api/v1/webhook | Register Webhook ( STABLE ) |


## `deleteWebhook()`

```php
deleteWebhook($v1_de_register_webhook_request): \TheLogicStudio\GrailPay\Model\DeleteWebhook200Response
```

De-register Webhook ( STABLE )

Deregistering a webhook via API involves removing a previously registered webhook configuration from the GrailPay. To disable notification related to particular transaction events, you need to de-register webhook with registered events name.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');



$apiInstance = new TheLogicStudio\GrailPay\Api\WebhooksApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client()
);
$v1_de_register_webhook_request = new \TheLogicStudio\GrailPay\Model\V1DeRegisterWebhookRequest(); // \TheLogicStudio\GrailPay\Model\V1DeRegisterWebhookRequest

try {
    $result = $apiInstance->deleteWebhook($v1_de_register_webhook_request);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling WebhooksApi->deleteWebhook: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **v1_de_register_webhook_request** | [**\TheLogicStudio\GrailPay\Model\V1DeRegisterWebhookRequest**](../Model/V1DeRegisterWebhookRequest.md)|  | |

### Return type

[**\TheLogicStudio\GrailPay\Model\DeleteWebhook200Response**](../Model/DeleteWebhook200Response.md)

### Authorization

No authorization required

### HTTP request headers

- **Content-Type**: `application/json`
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `getWebhook()`

```php
getWebhook(): \TheLogicStudio\GrailPay\Model\GetWebhook200Response
```

Get registered webhooks ( STABLE )

Retrieve a list of registered webhooks for the authenticated user.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');



$apiInstance = new TheLogicStudio\GrailPay\Api\WebhooksApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client()
);

try {
    $result = $apiInstance->getWebhook();
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling WebhooksApi->getWebhook: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

This endpoint does not need any parameter.

### Return type

[**\TheLogicStudio\GrailPay\Model\GetWebhook200Response**](../Model/GetWebhook200Response.md)

### Authorization

No authorization required

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `postWebhook()`

```php
postWebhook($v1_register_webhook_request): \TheLogicStudio\GrailPay\Model\PostWebhook201Response
```

Register Webhook ( STABLE )

Registering a webhook via API call involves configuring a client application to receive notifications and updates from GrailPay. To enable notification related to transaction, you need to register webhook with sets of predefined Events.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');



$apiInstance = new TheLogicStudio\GrailPay\Api\WebhooksApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client()
);
$v1_register_webhook_request = new \TheLogicStudio\GrailPay\Model\V1RegisterWebhookRequest(); // \TheLogicStudio\GrailPay\Model\V1RegisterWebhookRequest

try {
    $result = $apiInstance->postWebhook($v1_register_webhook_request);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling WebhooksApi->postWebhook: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **v1_register_webhook_request** | [**\TheLogicStudio\GrailPay\Model\V1RegisterWebhookRequest**](../Model/V1RegisterWebhookRequest.md)|  | |

### Return type

[**\TheLogicStudio\GrailPay\Model\PostWebhook201Response**](../Model/PostWebhook201Response.md)

### Authorization

No authorization required

### HTTP request headers

- **Content-Type**: `application/json`
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)
