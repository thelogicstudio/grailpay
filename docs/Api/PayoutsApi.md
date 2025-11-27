# TheLogicStudio\GrailPay\PayoutsApi

API Endpoints used for fetching payout information.

All URIs are relative to https://api.grailpay.com, except if the operation defines another base path.

| Method | HTTP request | Description |
| ------------- | ------------- | ------------- |
| [**getBatchPayoutsBusiness()**](PayoutsApi.md#getBatchPayoutsBusiness) | **GET** /3p/api/v2/batch-payouts/business/{business_user_uuid}/{batch_payout_uuid} | Get Business Batch Payout ( STABLE ) |
| [**getBatchPayoutsMerchant()**](PayoutsApi.md#getBatchPayoutsMerchant) | **GET** /3p/api/v2/batch-payouts/merchant/{merchant_user_uuid}/{batch_payout_uuid} | Get Merchant Batch Payout ( STABLE ) |
| [**getBatchPayoutsPerson()**](PayoutsApi.md#getBatchPayoutsPerson) | **GET** /3p/api/v2/batch-payouts/person/{user_uuid}/{batch_payout_uuid} | Get Person Batch Payout ( STABLE ) |
| [**getBatchPayoutsProcessor()**](PayoutsApi.md#getBatchPayoutsProcessor) | **GET** /3p/api/v2/batch-payouts/processor/{batch_payout_uuid} | Get Processor Batch Payout ( STABLE ) |


## `getBatchPayoutsBusiness()`

```php
getBatchPayoutsBusiness($business_user_uuid, $batch_payout_uuid): \TheLogicStudio\GrailPay\Model\V2PayeeBatchPayoutResponse
```

Get Business Batch Payout ( STABLE )

This API retrieves the details of a business batch payout using the business user UUID and the unique batch payout UUID. The response provides comprehensive information about the payout, including the total amount and a detailed breakdown of the transactions.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');



$apiInstance = new TheLogicStudio\GrailPay\Api\PayoutsApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client()
);
$business_user_uuid = 'business_user_uuid_example'; // string | UUID of the business user
$batch_payout_uuid = 'batch_payout_uuid_example'; // string | UUID of the batch payout

try {
    $result = $apiInstance->getBatchPayoutsBusiness($business_user_uuid, $batch_payout_uuid);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling PayoutsApi->getBatchPayoutsBusiness: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **business_user_uuid** | **string**| UUID of the business user | |
| **batch_payout_uuid** | **string**| UUID of the batch payout | |

### Return type

[**\TheLogicStudio\GrailPay\Model\V2PayeeBatchPayoutResponse**](../Model/V2PayeeBatchPayoutResponse.md)

### Authorization

No authorization required

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `getBatchPayoutsMerchant()`

```php
getBatchPayoutsMerchant($merchant_user_uuid, $batch_payout_uuid): \TheLogicStudio\GrailPay\Model\V2PayeeBatchPayoutResponse
```

Get Merchant Batch Payout ( STABLE )

This API retrieves the details of a merchant batch payout using the merchant user UUID and the unique batch payout UUID. The response provides comprehensive information about the payout, including the total amount and a detailed breakdown of the transactions.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');



$apiInstance = new TheLogicStudio\GrailPay\Api\PayoutsApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client()
);
$merchant_user_uuid = 'merchant_user_uuid_example'; // string | UUID of the merchant
$batch_payout_uuid = 'batch_payout_uuid_example'; // string | UUID of the batch payout

try {
    $result = $apiInstance->getBatchPayoutsMerchant($merchant_user_uuid, $batch_payout_uuid);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling PayoutsApi->getBatchPayoutsMerchant: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **merchant_user_uuid** | **string**| UUID of the merchant | |
| **batch_payout_uuid** | **string**| UUID of the batch payout | |

### Return type

[**\TheLogicStudio\GrailPay\Model\V2PayeeBatchPayoutResponse**](../Model/V2PayeeBatchPayoutResponse.md)

### Authorization

No authorization required

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `getBatchPayoutsPerson()`

```php
getBatchPayoutsPerson($user_uuid, $batch_payout_uuid): \TheLogicStudio\GrailPay\Model\V2PayeeBatchPayoutResponse
```

Get Person Batch Payout ( STABLE )

This API retrieves the details of a person batch payout using the person user UUID and the unique batch payout UUID. The response provides comprehensive information about the payout, including the total amount and a detailed breakdown of the transactions.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');



$apiInstance = new TheLogicStudio\GrailPay\Api\PayoutsApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client()
);
$user_uuid = 'user_uuid_example'; // string | UUID of the user
$batch_payout_uuid = 'batch_payout_uuid_example'; // string | UUID of the batch payout

try {
    $result = $apiInstance->getBatchPayoutsPerson($user_uuid, $batch_payout_uuid);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling PayoutsApi->getBatchPayoutsPerson: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **user_uuid** | **string**| UUID of the user | |
| **batch_payout_uuid** | **string**| UUID of the batch payout | |

### Return type

[**\TheLogicStudio\GrailPay\Model\V2PayeeBatchPayoutResponse**](../Model/V2PayeeBatchPayoutResponse.md)

### Authorization

No authorization required

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `getBatchPayoutsProcessor()`

```php
getBatchPayoutsProcessor($batch_payout_uuid): \TheLogicStudio\GrailPay\Model\V2ProcessorBatchPayoutResponse
```

Get Processor Batch Payout ( STABLE )

This API retrieves the details of a processor batch payout using the unique batch payout UUID. The response provides comprehensive information about the payout, including the total amount and a detailed breakdown of the transactions.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');



$apiInstance = new TheLogicStudio\GrailPay\Api\PayoutsApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client()
);
$batch_payout_uuid = 'batch_payout_uuid_example'; // string | UUID of the batch payout

try {
    $result = $apiInstance->getBatchPayoutsProcessor($batch_payout_uuid);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling PayoutsApi->getBatchPayoutsProcessor: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **batch_payout_uuid** | **string**| UUID of the batch payout | |

### Return type

[**\TheLogicStudio\GrailPay\Model\V2ProcessorBatchPayoutResponse**](../Model/V2ProcessorBatchPayoutResponse.md)

### Authorization

No authorization required

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)
