# TheLogicStudio\GrailPay\PayoutsApi

API Endpoints used for fetching payout information.

All URIs are relative to https://api.grailpay.com, except if the operation defines another base path.

| Method | HTTP request | Description |
| ------------- | ------------- | ------------- |
| [**getBatchMerchantPayoutsByBatchMerchantPayoutUuid()**](PayoutsApi.md#getBatchMerchantPayoutsByBatchMerchantPayoutUuid) | **GET** /3p/api/v2/batch-merchant-payouts/{batch_merchant_payout_uuid} | Get Batch Merchant Payout ( SUNSETTING ) |
| [**getBatchPayouts()**](PayoutsApi.md#getBatchPayouts) | **GET** /3p/api/v2/batch-payouts | Get All Batch Payouts ( SUNSETTING ) |
| [**getBatchPayoutsBusinessByBusinessUserUuid()**](PayoutsApi.md#getBatchPayoutsBusinessByBusinessUserUuid) | **GET** /3p/api/v2/batch-payouts/business/{business_user_uuid} | List Business Batch Payouts ( STABLE ) |
| [**getBatchPayoutsBusinessByBusinessUserUuidByBatchPayoutUuid()**](PayoutsApi.md#getBatchPayoutsBusinessByBusinessUserUuidByBatchPayoutUuid) | **GET** /3p/api/v2/batch-payouts/business/{business_user_uuid}/{batch_payout_uuid} | Get Business Batch Payout ( STABLE ) |
| [**getBatchPayoutsByBatchPayoutUuid()**](PayoutsApi.md#getBatchPayoutsByBatchPayoutUuid) | **GET** /3p/api/v2/batch-payouts/{batch_payout_uuid} | Get Batch Payout ( SUNSETTING ) |
| [**getBatchPayoutsMerchantByMerchantUserUuid()**](PayoutsApi.md#getBatchPayoutsMerchantByMerchantUserUuid) | **GET** /3p/api/v2/batch-payouts/merchant/{merchant_user_uuid} | List Merchant Batch Payouts ( STABLE ) |
| [**getBatchPayoutsMerchantByMerchantUserUuidByBatchPayoutUuid()**](PayoutsApi.md#getBatchPayoutsMerchantByMerchantUserUuidByBatchPayoutUuid) | **GET** /3p/api/v2/batch-payouts/merchant/{merchant_user_uuid}/{batch_payout_uuid} | Get Merchant Batch Payout ( STABLE ) |
| [**getBatchPayoutsPersonByUserUuid()**](PayoutsApi.md#getBatchPayoutsPersonByUserUuid) | **GET** /3p/api/v2/batch-payouts/person/{user_uuid} | List Person Batch Payouts ( STABLE ) |
| [**getBatchPayoutsPersonByUserUuidByBatchPayoutUuid()**](PayoutsApi.md#getBatchPayoutsPersonByUserUuidByBatchPayoutUuid) | **GET** /3p/api/v2/batch-payouts/person/{user_uuid}/{batch_payout_uuid} | Get Person Batch Payout ( STABLE ) |
| [**getProcessorBatchPayouts()**](PayoutsApi.md#getProcessorBatchPayouts) | **GET** /3p/api/v2/batch-payouts/processor | List Processor Batch Payouts ( STABLE ) |
| [**getProcessorBatchPayoutsByBatchPayoutUuid()**](PayoutsApi.md#getProcessorBatchPayoutsByBatchPayoutUuid) | **GET** /3p/api/v2/batch-payouts/processor/{batch_payout_uuid} | Get Processor Batch Payout ( STABLE ) |


## `getBatchMerchantPayoutsByBatchMerchantPayoutUuid()`

```php
getBatchMerchantPayoutsByBatchMerchantPayoutUuid($batch_merchant_payout_uuid): \TheLogicStudio\GrailPay\Model\GetBatchMerchantPayoutsByBatchMerchantPayoutUuid200Response
```

Get Batch Merchant Payout ( SUNSETTING )

**This Endpoint is Sunsetting and you should use the stable endpoint.  Sunsetting APIs that are still supported but scheduled for deprecation.**GrailPay enables merchants to receive a single batch payout per day, consolidating multiple transactions into one payout instead of processing individual transfers separately. This helps streamline payments and reduce transaction costs.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (Token) authorization: APIToken
$config = TheLogicStudio\GrailPay\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new TheLogicStudio\GrailPay\Api\PayoutsApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$batch_merchant_payout_uuid = 9bd53fe1-ac74-4e81-b6f2-be88b7c86a68; // string | UUID of the batch merchant payout

try {
    $result = $apiInstance->getBatchMerchantPayoutsByBatchMerchantPayoutUuid($batch_merchant_payout_uuid);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling PayoutsApi->getBatchMerchantPayoutsByBatchMerchantPayoutUuid: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **batch_merchant_payout_uuid** | **string**| UUID of the batch merchant payout | |

### Return type

[**\TheLogicStudio\GrailPay\Model\GetBatchMerchantPayoutsByBatchMerchantPayoutUuid200Response**](../Model/GetBatchMerchantPayoutsByBatchMerchantPayoutUuid200Response.md)

### Authorization

[APIToken](../../README.md#APIToken)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `getBatchPayouts()`

```php
getBatchPayouts($start_date, $end_date, $sort_order, $page, $per_page): \TheLogicStudio\GrailPay\Model\GetBatchPayouts200Response
```

Get All Batch Payouts ( SUNSETTING )

**This Endpoint is Sunsetting and you should use the stable endpoint.  Sunsetting APIs that are still supported but scheduled for deprecation.** This API retrieves a list of all batch payouts. The response provides details for each payout, including the total amount and relevant timestamps. Pagination options are available to efficiently manage large datasets.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (Token) authorization: APIToken
$config = TheLogicStudio\GrailPay\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new TheLogicStudio\GrailPay\Api\PayoutsApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$start_date = new \DateTime('2013-10-20T19:20:30+01:00'); // \DateTime | Filter by start date (YYYY-MM-DD)
$end_date = new \DateTime('2013-10-20T19:20:30+01:00'); // \DateTime | Filter by end date (YYYY-MM-DD)
$sort_order = 'sort_order_example'; // string | Sort order ('oldest' or 'newest')
$page = 1; // int | Page number for pagination
$per_page = 10; // int | Number of records per page

try {
    $result = $apiInstance->getBatchPayouts($start_date, $end_date, $sort_order, $page, $per_page);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling PayoutsApi->getBatchPayouts: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **start_date** | **\DateTime**| Filter by start date (YYYY-MM-DD) | [optional] |
| **end_date** | **\DateTime**| Filter by end date (YYYY-MM-DD) | [optional] |
| **sort_order** | **string**| Sort order (&#39;oldest&#39; or &#39;newest&#39;) | [optional] |
| **page** | **int**| Page number for pagination | [optional] |
| **per_page** | **int**| Number of records per page | [optional] |

### Return type

[**\TheLogicStudio\GrailPay\Model\GetBatchPayouts200Response**](../Model/GetBatchPayouts200Response.md)

### Authorization

[APIToken](../../README.md#APIToken)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `getBatchPayoutsBusinessByBusinessUserUuid()`

```php
getBatchPayoutsBusinessByBusinessUserUuid($business_user_uuid, $start_date, $end_date, $sort_order, $page, $per_page): \TheLogicStudio\GrailPay\Model\V2PayeeBatchPayoutsResponse
```

List Business Batch Payouts ( STABLE )

This API retrieves all business batch payouts associated with the business user UUID. The response provides comprehensive details about each payout, including the total amount and detailed information for each payout.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (Token) authorization: APIToken
$config = TheLogicStudio\GrailPay\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new TheLogicStudio\GrailPay\Api\PayoutsApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$business_user_uuid = 'business_user_uuid_example'; // string | UUID of the business user
$start_date = new \DateTime('2013-10-20T19:20:30+01:00'); // \DateTime | Filter by start date (YYYY-MM-DD)
$end_date = new \DateTime('2013-10-20T19:20:30+01:00'); // \DateTime | Filter by end date (YYYY-MM-DD)
$sort_order = 'sort_order_example'; // string | Sort order ('oldest' or 'newest')
$page = 1; // int | Page number for pagination
$per_page = 10; // int | Number of records per page

try {
    $result = $apiInstance->getBatchPayoutsBusinessByBusinessUserUuid($business_user_uuid, $start_date, $end_date, $sort_order, $page, $per_page);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling PayoutsApi->getBatchPayoutsBusinessByBusinessUserUuid: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **business_user_uuid** | **string**| UUID of the business user | |
| **start_date** | **\DateTime**| Filter by start date (YYYY-MM-DD) | [optional] |
| **end_date** | **\DateTime**| Filter by end date (YYYY-MM-DD) | [optional] |
| **sort_order** | **string**| Sort order (&#39;oldest&#39; or &#39;newest&#39;) | [optional] |
| **page** | **int**| Page number for pagination | [optional] |
| **per_page** | **int**| Number of records per page | [optional] |

### Return type

[**\TheLogicStudio\GrailPay\Model\V2PayeeBatchPayoutsResponse**](../Model/V2PayeeBatchPayoutsResponse.md)

### Authorization

[APIToken](../../README.md#APIToken)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `getBatchPayoutsBusinessByBusinessUserUuidByBatchPayoutUuid()`

```php
getBatchPayoutsBusinessByBusinessUserUuidByBatchPayoutUuid($business_user_uuid, $batch_payout_uuid): \TheLogicStudio\GrailPay\Model\V2PayeeBatchPayoutResponse
```

Get Business Batch Payout ( STABLE )

This API retrieves the details of a business batch payout using the business user UUID and the unique batch payout UUID. The response provides comprehensive information about the payout, including the total amount and a detailed breakdown of the transactions.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (Token) authorization: APIToken
$config = TheLogicStudio\GrailPay\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new TheLogicStudio\GrailPay\Api\PayoutsApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$business_user_uuid = 'business_user_uuid_example'; // string | UUID of the business user
$batch_payout_uuid = 'batch_payout_uuid_example'; // string | UUID of the batch payout

try {
    $result = $apiInstance->getBatchPayoutsBusinessByBusinessUserUuidByBatchPayoutUuid($business_user_uuid, $batch_payout_uuid);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling PayoutsApi->getBatchPayoutsBusinessByBusinessUserUuidByBatchPayoutUuid: ', $e->getMessage(), PHP_EOL;
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

[APIToken](../../README.md#APIToken)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `getBatchPayoutsByBatchPayoutUuid()`

```php
getBatchPayoutsByBatchPayoutUuid($batch_payout_uuid): \TheLogicStudio\GrailPay\Model\GetBatchPayoutsByBatchPayoutUuid200Response
```

Get Batch Payout ( SUNSETTING )

**This Endpoint is Sunsetting and you should use the stable endpoint.  Sunsetting APIs that are still supported but scheduled for deprecation.** This API retrieves the details of a specific batch payout using its unique batch payout UUID. The response provides comprehensive information about the payout, including the total amount and a breakdown of transactions grouped by payee.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (Token) authorization: APIToken
$config = TheLogicStudio\GrailPay\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new TheLogicStudio\GrailPay\Api\PayoutsApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$batch_payout_uuid = 'batch_payout_uuid_example'; // string | UUID of the batch payout

try {
    $result = $apiInstance->getBatchPayoutsByBatchPayoutUuid($batch_payout_uuid);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling PayoutsApi->getBatchPayoutsByBatchPayoutUuid: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **batch_payout_uuid** | **string**| UUID of the batch payout | |

### Return type

[**\TheLogicStudio\GrailPay\Model\GetBatchPayoutsByBatchPayoutUuid200Response**](../Model/GetBatchPayoutsByBatchPayoutUuid200Response.md)

### Authorization

[APIToken](../../README.md#APIToken)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `getBatchPayoutsMerchantByMerchantUserUuid()`

```php
getBatchPayoutsMerchantByMerchantUserUuid($merchant_user_uuid, $start_date, $end_date, $sort_order, $page, $per_page): \TheLogicStudio\GrailPay\Model\V2PayeeBatchPayoutsResponse
```

List Merchant Batch Payouts ( STABLE )

This API retrieves all merchant batch payouts associated with the merchant user UUID. The response provides comprehensive details about each payout, including the total amount and detailed information for each individual payout.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (Token) authorization: APIToken
$config = TheLogicStudio\GrailPay\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new TheLogicStudio\GrailPay\Api\PayoutsApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$merchant_user_uuid = 'merchant_user_uuid_example'; // string | UUID of the merchant
$start_date = new \DateTime('2013-10-20T19:20:30+01:00'); // \DateTime | Filter by start date (YYYY-MM-DD)
$end_date = new \DateTime('2013-10-20T19:20:30+01:00'); // \DateTime | Filter by end date (YYYY-MM-DD)
$sort_order = 'sort_order_example'; // string | Sort order ('oldest' or 'newest')
$page = 1; // int | Page number for pagination
$per_page = 10; // int | Number of records per page

try {
    $result = $apiInstance->getBatchPayoutsMerchantByMerchantUserUuid($merchant_user_uuid, $start_date, $end_date, $sort_order, $page, $per_page);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling PayoutsApi->getBatchPayoutsMerchantByMerchantUserUuid: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **merchant_user_uuid** | **string**| UUID of the merchant | |
| **start_date** | **\DateTime**| Filter by start date (YYYY-MM-DD) | [optional] |
| **end_date** | **\DateTime**| Filter by end date (YYYY-MM-DD) | [optional] |
| **sort_order** | **string**| Sort order (&#39;oldest&#39; or &#39;newest&#39;) | [optional] |
| **page** | **int**| Page number for pagination | [optional] |
| **per_page** | **int**| Number of records per page | [optional] |

### Return type

[**\TheLogicStudio\GrailPay\Model\V2PayeeBatchPayoutsResponse**](../Model/V2PayeeBatchPayoutsResponse.md)

### Authorization

[APIToken](../../README.md#APIToken)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `getBatchPayoutsMerchantByMerchantUserUuidByBatchPayoutUuid()`

```php
getBatchPayoutsMerchantByMerchantUserUuidByBatchPayoutUuid($merchant_user_uuid, $batch_payout_uuid): \TheLogicStudio\GrailPay\Model\V2PayeeBatchPayoutResponse
```

Get Merchant Batch Payout ( STABLE )

This API retrieves the details of a merchant batch payout using the merchant user UUID and the unique batch payout UUID. The response provides comprehensive information about the payout, including the total amount and a detailed breakdown of the transactions.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (Token) authorization: APIToken
$config = TheLogicStudio\GrailPay\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new TheLogicStudio\GrailPay\Api\PayoutsApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$merchant_user_uuid = 'merchant_user_uuid_example'; // string | UUID of the merchant
$batch_payout_uuid = 'batch_payout_uuid_example'; // string | UUID of the batch payout

try {
    $result = $apiInstance->getBatchPayoutsMerchantByMerchantUserUuidByBatchPayoutUuid($merchant_user_uuid, $batch_payout_uuid);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling PayoutsApi->getBatchPayoutsMerchantByMerchantUserUuidByBatchPayoutUuid: ', $e->getMessage(), PHP_EOL;
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

[APIToken](../../README.md#APIToken)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `getBatchPayoutsPersonByUserUuid()`

```php
getBatchPayoutsPersonByUserUuid($user_uuid, $start_date, $end_date, $sort_order, $page, $per_page): \TheLogicStudio\GrailPay\Model\V2PayeeBatchPayoutsResponse
```

List Person Batch Payouts ( STABLE )

This API retrieves all person batch payouts associated with the person user UUID. The response provides comprehensive details about each payout, including the total amount and detailed information for each payout.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (Token) authorization: APIToken
$config = TheLogicStudio\GrailPay\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new TheLogicStudio\GrailPay\Api\PayoutsApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$user_uuid = 'user_uuid_example'; // string | UUID of the user
$start_date = new \DateTime('2013-10-20T19:20:30+01:00'); // \DateTime | Filter by start date (YYYY-MM-DD)
$end_date = new \DateTime('2013-10-20T19:20:30+01:00'); // \DateTime | Filter by end date (YYYY-MM-DD)
$sort_order = 'sort_order_example'; // string | Sort order ('oldest' or 'newest')
$page = 1; // int | Page number for pagination
$per_page = 10; // int | Number of records per page

try {
    $result = $apiInstance->getBatchPayoutsPersonByUserUuid($user_uuid, $start_date, $end_date, $sort_order, $page, $per_page);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling PayoutsApi->getBatchPayoutsPersonByUserUuid: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **user_uuid** | **string**| UUID of the user | |
| **start_date** | **\DateTime**| Filter by start date (YYYY-MM-DD) | [optional] |
| **end_date** | **\DateTime**| Filter by end date (YYYY-MM-DD) | [optional] |
| **sort_order** | **string**| Sort order (&#39;oldest&#39; or &#39;newest&#39;) | [optional] |
| **page** | **int**| Page number for pagination | [optional] |
| **per_page** | **int**| Number of records per page | [optional] |

### Return type

[**\TheLogicStudio\GrailPay\Model\V2PayeeBatchPayoutsResponse**](../Model/V2PayeeBatchPayoutsResponse.md)

### Authorization

[APIToken](../../README.md#APIToken)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `getBatchPayoutsPersonByUserUuidByBatchPayoutUuid()`

```php
getBatchPayoutsPersonByUserUuidByBatchPayoutUuid($user_uuid, $batch_payout_uuid): \TheLogicStudio\GrailPay\Model\V2PayeeBatchPayoutResponse
```

Get Person Batch Payout ( STABLE )

This API retrieves the details of a person batch payout using the person user UUID and the unique batch payout UUID. The response provides comprehensive information about the payout, including the total amount and a detailed breakdown of the transactions.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (Token) authorization: APIToken
$config = TheLogicStudio\GrailPay\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new TheLogicStudio\GrailPay\Api\PayoutsApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$user_uuid = 'user_uuid_example'; // string | UUID of the user
$batch_payout_uuid = 'batch_payout_uuid_example'; // string | UUID of the batch payout

try {
    $result = $apiInstance->getBatchPayoutsPersonByUserUuidByBatchPayoutUuid($user_uuid, $batch_payout_uuid);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling PayoutsApi->getBatchPayoutsPersonByUserUuidByBatchPayoutUuid: ', $e->getMessage(), PHP_EOL;
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

[APIToken](../../README.md#APIToken)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `getProcessorBatchPayouts()`

```php
getProcessorBatchPayouts($start_date, $end_date, $sort_order, $page, $per_page): \TheLogicStudio\GrailPay\Model\V2ProcessorBatchPayoutsResponse
```

List Processor Batch Payouts ( STABLE )

This API retrieves all batch payouts associated with the processor. The response provides comprehensive details for each payout, including the total amount and specific information for each payout.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (Token) authorization: APIToken
$config = TheLogicStudio\GrailPay\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new TheLogicStudio\GrailPay\Api\PayoutsApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$start_date = new \DateTime('2013-10-20T19:20:30+01:00'); // \DateTime | Filter by start date (YYYY-MM-DD)
$end_date = new \DateTime('2013-10-20T19:20:30+01:00'); // \DateTime | Filter by end date (YYYY-MM-DD)
$sort_order = 'sort_order_example'; // string | Sort order ('oldest' or 'newest')
$page = 1; // int | Page number for pagination
$per_page = 10; // int | Number of records per page

try {
    $result = $apiInstance->getProcessorBatchPayouts($start_date, $end_date, $sort_order, $page, $per_page);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling PayoutsApi->getProcessorBatchPayouts: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **start_date** | **\DateTime**| Filter by start date (YYYY-MM-DD) | [optional] |
| **end_date** | **\DateTime**| Filter by end date (YYYY-MM-DD) | [optional] |
| **sort_order** | **string**| Sort order (&#39;oldest&#39; or &#39;newest&#39;) | [optional] |
| **page** | **int**| Page number for pagination | [optional] |
| **per_page** | **int**| Number of records per page | [optional] |

### Return type

[**\TheLogicStudio\GrailPay\Model\V2ProcessorBatchPayoutsResponse**](../Model/V2ProcessorBatchPayoutsResponse.md)

### Authorization

[APIToken](../../README.md#APIToken)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `getProcessorBatchPayoutsByBatchPayoutUuid()`

```php
getProcessorBatchPayoutsByBatchPayoutUuid($batch_payout_uuid): \TheLogicStudio\GrailPay\Model\V2ProcessorBatchPayoutResponse
```

Get Processor Batch Payout ( STABLE )

This API retrieves the details of a processor batch payout using the unique batch payout UUID. The response provides comprehensive information about the payout, including the total amount and a detailed breakdown of the transactions.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (Token) authorization: APIToken
$config = TheLogicStudio\GrailPay\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new TheLogicStudio\GrailPay\Api\PayoutsApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$batch_payout_uuid = 'batch_payout_uuid_example'; // string | UUID of the batch payout

try {
    $result = $apiInstance->getProcessorBatchPayoutsByBatchPayoutUuid($batch_payout_uuid);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling PayoutsApi->getProcessorBatchPayoutsByBatchPayoutUuid: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **batch_payout_uuid** | **string**| UUID of the batch payout | |

### Return type

[**\TheLogicStudio\GrailPay\Model\V2ProcessorBatchPayoutResponse**](../Model/V2ProcessorBatchPayoutResponse.md)

### Authorization

[APIToken](../../README.md#APIToken)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)
