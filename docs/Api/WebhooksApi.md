# TheLogicStudio\GrailPay\WebhooksApi

API Endpoints used for registering and de-registering webhooks.

All URIs are relative to https://api.grailpay.com, except if the operation defines another base path.

| Method | HTTP request | Description |
| ------------- | ------------- | ------------- |
| [**deleteWebhooksByUuid()**](WebhooksApi.md#deleteWebhooksByUuid) | **DELETE** /api/v3/webhooks/{uuid} | Delete Webhook |
| [**getWebhooks()**](WebhooksApi.md#getWebhooks) | **GET** /api/v3/webhooks | Get All Webhooks |
| [**getWebhooksByUuid()**](WebhooksApi.md#getWebhooksByUuid) | **GET** /api/v3/webhooks/{uuid} | Get Webhook |
| [**postWebhooks()**](WebhooksApi.md#postWebhooks) | **POST** /api/v3/webhooks | Register Webhook |


## `deleteWebhooksByUuid()`

```php
deleteWebhooksByUuid($uuid): \TheLogicStudio\GrailPay\Model\DeleteWebhooksByUuid200Response
```

Delete Webhook

Deletes a webhook registration that belongs to the authenticated vendor or processor. Events are no longer delivered to its URL, and requesting the registration afterwards returns 404.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (Token) authorization: ApiToken
$config = TheLogicStudio\GrailPay\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new TheLogicStudio\GrailPay\Api\WebhooksApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$uuid = 0199b6a2-4c1e-7d3a-9f2b-6e8d1c5a7b30; // string | Webhook registration UUID

try {
    $result = $apiInstance->deleteWebhooksByUuid($uuid);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling WebhooksApi->deleteWebhooksByUuid: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **uuid** | **string**| Webhook registration UUID | |

### Return type

[**\TheLogicStudio\GrailPay\Model\DeleteWebhooksByUuid200Response**](../Model/DeleteWebhooksByUuid200Response.md)

### Authorization

[ApiToken](../../README.md#ApiToken)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `getWebhooks()`

```php
getWebhooks($filter_is_active, $filter_url, $sort, $page, $per_page): \TheLogicStudio\GrailPay\Model\GetWebhooks200Response
```

Get All Webhooks

This endpoint returns a paginated list of the webhook registrations that belong to the authenticated vendor or processor, with filtering and sorting options. Deleted registrations are not included.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (Token) authorization: ApiToken
$config = TheLogicStudio\GrailPay\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new TheLogicStudio\GrailPay\Api\WebhooksApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$filter_is_active = true; // bool | Filter by whether the registration is active
$filter_url = example.com; // string | Filter by URL (case-insensitive partial match)
$sort = -created_at; // string | Sort by created_at. Prefix with '-' for descending order (the default)
$page = 1; // int | Page number for pagination
$per_page = 15; // int | Number of records per page

try {
    $result = $apiInstance->getWebhooks($filter_is_active, $filter_url, $sort, $page, $per_page);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling WebhooksApi->getWebhooks: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **filter_is_active** | **bool**| Filter by whether the registration is active | [optional] |
| **filter_url** | **string**| Filter by URL (case-insensitive partial match) | [optional] |
| **sort** | **string**| Sort by created_at. Prefix with &#39;-&#39; for descending order (the default) | [optional] |
| **page** | **int**| Page number for pagination | [optional] |
| **per_page** | **int**| Number of records per page | [optional] [default to 15] |

### Return type

[**\TheLogicStudio\GrailPay\Model\GetWebhooks200Response**](../Model/GetWebhooks200Response.md)

### Authorization

[ApiToken](../../README.md#ApiToken)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `getWebhooksByUuid()`

```php
getWebhooksByUuid($uuid): \TheLogicStudio\GrailPay\Model\GetWebhooksByUuid200Response
```

Get Webhook

Retrieves a single webhook registration that belongs to the authenticated vendor or processor, including its signing `secret`.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (Token) authorization: ApiToken
$config = TheLogicStudio\GrailPay\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new TheLogicStudio\GrailPay\Api\WebhooksApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$uuid = 0199b6a2-4c1e-7d3a-9f2b-6e8d1c5a7b30; // string | Webhook registration UUID

try {
    $result = $apiInstance->getWebhooksByUuid($uuid);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling WebhooksApi->getWebhooksByUuid: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **uuid** | **string**| Webhook registration UUID | |

### Return type

[**\TheLogicStudio\GrailPay\Model\GetWebhooksByUuid200Response**](../Model/GetWebhooksByUuid200Response.md)

### Authorization

[ApiToken](../../README.md#ApiToken)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `postWebhooks()`

```php
postWebhooks($post_webhooks_request, $idempotency_key): \TheLogicStudio\GrailPay\Model\PostWebhooks201Response
```

Register Webhook

Registers an HTTPS URL to receive webhook events for the authenticated vendor or processor. This replaces the deprecated `/3p/api/v1/webhook` and `/processor/api/v1/webhook` registration endpoints. The response includes the registration's `secret`: every delivery carries a `Signature` header containing the hex-encoded HMAC-SHA256 of the raw JSON request body, keyed with this secret, so you can verify the delivery came from GrailPay. A URL can be registered once per vendor or processor, with up to 25 registrations each. Only `url` is accepted in the request body. Supports idempotency via the `Idempotency-Key` header.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (Token) authorization: ApiToken
$config = TheLogicStudio\GrailPay\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new TheLogicStudio\GrailPay\Api\WebhooksApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$post_webhooks_request = new \TheLogicStudio\GrailPay\Model\PostWebhooksRequest(); // \TheLogicStudio\GrailPay\Model\PostWebhooksRequest
$idempotency_key = webhook-idempotency-key-123; // string | Optional idempotency key. Replaying the same key with the same request body returns the original response; a conflicting body returns 409.

try {
    $result = $apiInstance->postWebhooks($post_webhooks_request, $idempotency_key);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling WebhooksApi->postWebhooks: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **post_webhooks_request** | [**\TheLogicStudio\GrailPay\Model\PostWebhooksRequest**](../Model/PostWebhooksRequest.md)|  | |
| **idempotency_key** | **string**| Optional idempotency key. Replaying the same key with the same request body returns the original response; a conflicting body returns 409. | [optional] |

### Return type

[**\TheLogicStudio\GrailPay\Model\PostWebhooks201Response**](../Model/PostWebhooks201Response.md)

### Authorization

[ApiToken](../../README.md#ApiToken)

### HTTP request headers

- **Content-Type**: `application/json`
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)
