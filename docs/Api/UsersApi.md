# TheLogicStudio\GrailPay\UsersApi

API Endpoints used for the onboarding and managing People, Businesses, and Merchants.

All URIs are relative to https://api.grailpay.com, except if the operation defines another base path.

| Method | HTTP request | Description |
| ------------- | ------------- | ------------- |
| [**deletePeopleByUuid()**](UsersApi.md#deletePeopleByUuid) | **DELETE** /api/v3/people/{uuid} | Delete Person |
| [**getBusinesses()**](UsersApi.md#getBusinesses) | **GET** /api/v3/businesses | Get All Businesses |
| [**getBusinessesByUuid()**](UsersApi.md#getBusinessesByUuid) | **GET** /api/v3/businesses/{uuid} | Get Business |
| [**getMerchants()**](UsersApi.md#getMerchants) | **GET** /api/v3/merchants | Get All Merchants |
| [**getMerchantsByUuid()**](UsersApi.md#getMerchantsByUuid) | **GET** /api/v3/merchants/{uuid} | Get Merchant |
| [**getPeople()**](UsersApi.md#getPeople) | **GET** /api/v3/people | Get All People |
| [**getPeopleByUuid()**](UsersApi.md#getPeopleByUuid) | **GET** /api/v3/people/{uuid} | Get Person |
| [**patchBusinessesByUuid()**](UsersApi.md#patchBusinessesByUuid) | **PATCH** /api/v3/businesses/{uuid} | Update a Business into the ACH application |
| [**patchMerchantsByUuid()**](UsersApi.md#patchMerchantsByUuid) | **PATCH** /api/v3/merchants/{uuid} | Update a Merchant into the ACH application |
| [**patchPeopleByUuid()**](UsersApi.md#patchPeopleByUuid) | **PATCH** /api/v3/people/{uuid} | Update a Person into the ACH application |
| [**postBusinesses()**](UsersApi.md#postBusinesses) | **POST** /api/v3/businesses | Onboard a new Business into the ACH application |
| [**postMerchants()**](UsersApi.md#postMerchants) | **POST** /api/v3/merchants | Onboard a new Merchant into the ACH application |
| [**postMerchantsByUuidActivate()**](UsersApi.md#postMerchantsByUuidActivate) | **POST** /api/v3/merchants/{uuid}/activate | Activate a Merchant |
| [**postMerchantsByUuidDeactivate()**](UsersApi.md#postMerchantsByUuidDeactivate) | **POST** /api/v3/merchants/{uuid}/deactivate | Deactivate a Merchant |
| [**postPeople()**](UsersApi.md#postPeople) | **POST** /api/v3/people | Onboard a new Person into the ACH application |
| [**postPeopleKyc()**](UsersApi.md#postPeopleKyc) | **POST** /api/v3/people/kyc | Register Person KYC |


## `deletePeopleByUuid()`

```php
deletePeopleByUuid($uuid): \TheLogicStudio\GrailPay\Model\DeletePeopleByUuid202Response
```

Delete Person

This endpoint schedules a person for deletion. The person is not removed immediately: they are marked as scheduled for deletion, after which requests for that person return 403, and their email address is released so it can be registered again. The API token must belong to the vendor that owns the person, or to the processor of that vendor. Only people can be deleted with this endpoint.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (Token) authorization: ApiToken
$config = TheLogicStudio\GrailPay\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new TheLogicStudio\GrailPay\Api\UsersApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$uuid = 7c41f6a2-a4b9-4df8-9225-2c1b7312042e; // string | person UUID

try {
    $result = $apiInstance->deletePeopleByUuid($uuid);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling UsersApi->deletePeopleByUuid: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **uuid** | **string**| person UUID | |

### Return type

[**\TheLogicStudio\GrailPay\Model\DeletePeopleByUuid202Response**](../Model/DeletePeopleByUuid202Response.md)

### Authorization

[ApiToken](../../README.md#ApiToken)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `getBusinesses()`

```php
getBusinesses($filter_uuid, $filter_name, $sort, $page, $per_page): \TheLogicStudio\GrailPay\Model\GetBusinesses200Response
```

Get All Businesses

This endpoint provides a comprehensive list of all registered businesses, including essential details. Pagination options are available to efficiently manage large datasets.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (Token) authorization: ApiToken
$config = TheLogicStudio\GrailPay\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new TheLogicStudio\GrailPay\Api\UsersApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$filter_uuid = 7c41f6a2-a4b9-4df8-9225-2c1b7312042e; // string | Filter by business UUID
$filter_name = John Inc; // string | Filter by business name
$sort = -created_at; // string | Sort by field (created_at, name). Prefix with '-' for descending order
$page = 1; // int | Page number for pagination
$per_page = 15; // int | Number of records per page

try {
    $result = $apiInstance->getBusinesses($filter_uuid, $filter_name, $sort, $page, $per_page);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling UsersApi->getBusinesses: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **filter_uuid** | **string**| Filter by business UUID | [optional] |
| **filter_name** | **string**| Filter by business name | [optional] |
| **sort** | **string**| Sort by field (created_at, name). Prefix with &#39;-&#39; for descending order | [optional] |
| **page** | **int**| Page number for pagination | [optional] |
| **per_page** | **int**| Number of records per page | [optional] [default to 15] |

### Return type

[**\TheLogicStudio\GrailPay\Model\GetBusinesses200Response**](../Model/GetBusinesses200Response.md)

### Authorization

[ApiToken](../../README.md#ApiToken)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `getBusinessesByUuid()`

```php
getBusinessesByUuid($uuid): \TheLogicStudio\GrailPay\Model\GetBusinessesByUuid200Response
```

Get Business

This endpoint will return detail of the business. When making a request to an API for a business's information, you typically need to provide a unique identifier UUID. The UUID is generated at the time of registration and is associated with the business's account.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (Token) authorization: ApiToken
$config = TheLogicStudio\GrailPay\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new TheLogicStudio\GrailPay\Api\UsersApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$uuid = 7c41f6a2-a4b9-4df8-9225-2c1b7312042e; // string | business UUID

try {
    $result = $apiInstance->getBusinessesByUuid($uuid);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling UsersApi->getBusinessesByUuid: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **uuid** | **string**| business UUID | |

### Return type

[**\TheLogicStudio\GrailPay\Model\GetBusinessesByUuid200Response**](../Model/GetBusinessesByUuid200Response.md)

### Authorization

[ApiToken](../../README.md#ApiToken)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `getMerchants()`

```php
getMerchants($filter_uuid, $filter_name, $filter_tin, $sort, $page, $per_page): \TheLogicStudio\GrailPay\Model\GetMerchants200Response
```

Get All Merchants

This endpoint provides a comprehensive list of all registered merchants, including essential details. Pagination options are available to efficiently manage large datasets.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (Token) authorization: ApiToken
$config = TheLogicStudio\GrailPay\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new TheLogicStudio\GrailPay\Api\UsersApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$filter_uuid = 7c41f6a2-a4b9-4df8-9225-2c1b7312042e; // string | Filter by merchant UUID
$filter_name = John Inc; // string | Filter by merchant name
$filter_tin = 123456789; // string | Filter by EIN (TIN) number
$sort = -created_at; // string | Sort by field (created_at, name). Prefix with '-' for descending order
$page = 1; // int | Page number for pagination
$per_page = 15; // int | Number of records per page

try {
    $result = $apiInstance->getMerchants($filter_uuid, $filter_name, $filter_tin, $sort, $page, $per_page);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling UsersApi->getMerchants: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **filter_uuid** | **string**| Filter by merchant UUID | [optional] |
| **filter_name** | **string**| Filter by merchant name | [optional] |
| **filter_tin** | **string**| Filter by EIN (TIN) number | [optional] |
| **sort** | **string**| Sort by field (created_at, name). Prefix with &#39;-&#39; for descending order | [optional] |
| **page** | **int**| Page number for pagination | [optional] |
| **per_page** | **int**| Number of records per page | [optional] [default to 15] |

### Return type

[**\TheLogicStudio\GrailPay\Model\GetMerchants200Response**](../Model/GetMerchants200Response.md)

### Authorization

[ApiToken](../../README.md#ApiToken)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `getMerchantsByUuid()`

```php
getMerchantsByUuid($uuid): \TheLogicStudio\GrailPay\Model\GetMerchantsByUuid200Response
```

Get Merchant

This endpoint will return detail of the merchant. When making a request to an API for a merchant's information, you typically need to provide a unique identifier UUID. The UUID is generated at the time of registration and is associated with the merchant's account.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (Token) authorization: ApiToken
$config = TheLogicStudio\GrailPay\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new TheLogicStudio\GrailPay\Api\UsersApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$uuid = 7c41f6a2-a4b9-4df8-9225-2c1b7312042e; // string | merchant UUID

try {
    $result = $apiInstance->getMerchantsByUuid($uuid);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling UsersApi->getMerchantsByUuid: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **uuid** | **string**| merchant UUID | |

### Return type

[**\TheLogicStudio\GrailPay\Model\GetMerchantsByUuid200Response**](../Model/GetMerchantsByUuid200Response.md)

### Authorization

[ApiToken](../../README.md#ApiToken)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `getPeople()`

```php
getPeople($filter_uuid, $filter_client_reference_id, $filter_first_name, $filter_last_name, $sort, $page, $per_page): \TheLogicStudio\GrailPay\Model\GetPeople200Response
```

Get All People

This endpoint provides a comprehensive list of all registered people, including essential details. Pagination options are available to efficiently manage large datasets.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (Token) authorization: ApiToken
$config = TheLogicStudio\GrailPay\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new TheLogicStudio\GrailPay\Api\UsersApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$filter_uuid = 7c41f6a2-a4b9-4df8-9225-2c1b7312042e; // string | Filter by person UUID
$filter_client_reference_id = reference_12345; // string | Filter by client reference ID
$filter_first_name = John; // string | Filter by first name
$filter_last_name = Doe; // string | Filter by last name
$sort = -created_at; // string | Sort by field (created_at, first_name, last_name). Prefix with '-' for descending order
$page = 1; // int | Page number for pagination
$per_page = 15; // int | Number of records per page

try {
    $result = $apiInstance->getPeople($filter_uuid, $filter_client_reference_id, $filter_first_name, $filter_last_name, $sort, $page, $per_page);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling UsersApi->getPeople: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **filter_uuid** | **string**| Filter by person UUID | [optional] |
| **filter_client_reference_id** | **string**| Filter by client reference ID | [optional] |
| **filter_first_name** | **string**| Filter by first name | [optional] |
| **filter_last_name** | **string**| Filter by last name | [optional] |
| **sort** | **string**| Sort by field (created_at, first_name, last_name). Prefix with &#39;-&#39; for descending order | [optional] |
| **page** | **int**| Page number for pagination | [optional] |
| **per_page** | **int**| Number of records per page | [optional] [default to 15] |

### Return type

[**\TheLogicStudio\GrailPay\Model\GetPeople200Response**](../Model/GetPeople200Response.md)

### Authorization

[ApiToken](../../README.md#ApiToken)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `getPeopleByUuid()`

```php
getPeopleByUuid($uuid): \TheLogicStudio\GrailPay\Model\GetPeopleByUuid200Response
```

Get Person

This endpoint will return detail of the person. When making a request to an API for a person's information, you typically need to provide a unique identifier UUID. The UUID is generated at the time of registration and is associated with the person's account.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (Token) authorization: ApiToken
$config = TheLogicStudio\GrailPay\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new TheLogicStudio\GrailPay\Api\UsersApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$uuid = 7c41f6a2-a4b9-4df8-9225-2c1b7312042e; // string | person UUID

try {
    $result = $apiInstance->getPeopleByUuid($uuid);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling UsersApi->getPeopleByUuid: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **uuid** | **string**| person UUID | |

### Return type

[**\TheLogicStudio\GrailPay\Model\GetPeopleByUuid200Response**](../Model/GetPeopleByUuid200Response.md)

### Authorization

[ApiToken](../../README.md#ApiToken)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `patchBusinessesByUuid()`

```php
patchBusinessesByUuid($uuid, $post_businesses_request): \TheLogicStudio\GrailPay\Model\PatchBusinessesByUuid200Response
```

Update a Business into the ACH application

This endpoint allows for updating a Business to the GrailPay ACH API Ecosystem.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (Token) authorization: ApiToken
$config = TheLogicStudio\GrailPay\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new TheLogicStudio\GrailPay\Api\UsersApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$uuid = 7c41f6a2-a4b9-4df8-9225-2c1b7312042e; // string | business UUID
$post_businesses_request = new \TheLogicStudio\GrailPay\Model\PostBusinessesRequest(); // \TheLogicStudio\GrailPay\Model\PostBusinessesRequest

try {
    $result = $apiInstance->patchBusinessesByUuid($uuid, $post_businesses_request);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling UsersApi->patchBusinessesByUuid: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **uuid** | **string**| business UUID | |
| **post_businesses_request** | [**\TheLogicStudio\GrailPay\Model\PostBusinessesRequest**](../Model/PostBusinessesRequest.md)|  | |

### Return type

[**\TheLogicStudio\GrailPay\Model\PatchBusinessesByUuid200Response**](../Model/PatchBusinessesByUuid200Response.md)

### Authorization

[ApiToken](../../README.md#ApiToken)

### HTTP request headers

- **Content-Type**: `application/json`
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `patchMerchantsByUuid()`

```php
patchMerchantsByUuid($uuid, $post_merchants_request): \TheLogicStudio\GrailPay\Model\PatchMerchantsByUuid200Response
```

Update a Merchant into the ACH application

This endpoint allows for updating a Merchant to the GrailPay ACH API Ecosystem.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (Token) authorization: ApiToken
$config = TheLogicStudio\GrailPay\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new TheLogicStudio\GrailPay\Api\UsersApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$uuid = 7c41f6a2-a4b9-4df8-9225-2c1b7312042e; // string | merchant UUID
$post_merchants_request = new \TheLogicStudio\GrailPay\Model\PostMerchantsRequest(); // \TheLogicStudio\GrailPay\Model\PostMerchantsRequest

try {
    $result = $apiInstance->patchMerchantsByUuid($uuid, $post_merchants_request);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling UsersApi->patchMerchantsByUuid: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **uuid** | **string**| merchant UUID | |
| **post_merchants_request** | [**\TheLogicStudio\GrailPay\Model\PostMerchantsRequest**](../Model/PostMerchantsRequest.md)|  | |

### Return type

[**\TheLogicStudio\GrailPay\Model\PatchMerchantsByUuid200Response**](../Model/PatchMerchantsByUuid200Response.md)

### Authorization

[ApiToken](../../README.md#ApiToken)

### HTTP request headers

- **Content-Type**: `application/json`
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `patchPeopleByUuid()`

```php
patchPeopleByUuid($uuid, $post_people_request): \TheLogicStudio\GrailPay\Model\PatchPeopleByUuid200Response
```

Update a Person into the ACH application

This endpoint allows for updating a Person to the GrailPay ACH API Ecosystem.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (Token) authorization: ApiToken
$config = TheLogicStudio\GrailPay\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new TheLogicStudio\GrailPay\Api\UsersApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$uuid = 7c41f6a2-a4b9-4df8-9225-2c1b7312042e; // string | person UUID
$post_people_request = new \TheLogicStudio\GrailPay\Model\PostPeopleRequest(); // \TheLogicStudio\GrailPay\Model\PostPeopleRequest

try {
    $result = $apiInstance->patchPeopleByUuid($uuid, $post_people_request);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling UsersApi->patchPeopleByUuid: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **uuid** | **string**| person UUID | |
| **post_people_request** | [**\TheLogicStudio\GrailPay\Model\PostPeopleRequest**](../Model/PostPeopleRequest.md)|  | |

### Return type

[**\TheLogicStudio\GrailPay\Model\PatchPeopleByUuid200Response**](../Model/PatchPeopleByUuid200Response.md)

### Authorization

[ApiToken](../../README.md#ApiToken)

### HTTP request headers

- **Content-Type**: `application/json`
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `postBusinesses()`

```php
postBusinesses($post_businesses_request): \TheLogicStudio\GrailPay\Model\PostBusinesses201Response
```

Onboard a new Business into the ACH application

This endpoint allows for adding a new Business to the GrailPay ACH API Ecosystem.  The only item that is required is the Bank Account object, but we strongly encourage that you supply as much information as possible.  When including the bank account, you can pass either Plaid information or account and routing information.  You should never pass both.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (Token) authorization: ApiToken
$config = TheLogicStudio\GrailPay\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new TheLogicStudio\GrailPay\Api\UsersApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$post_businesses_request = new \TheLogicStudio\GrailPay\Model\PostBusinessesRequest(); // \TheLogicStudio\GrailPay\Model\PostBusinessesRequest

try {
    $result = $apiInstance->postBusinesses($post_businesses_request);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling UsersApi->postBusinesses: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **post_businesses_request** | [**\TheLogicStudio\GrailPay\Model\PostBusinessesRequest**](../Model/PostBusinessesRequest.md)|  | |

### Return type

[**\TheLogicStudio\GrailPay\Model\PostBusinesses201Response**](../Model/PostBusinesses201Response.md)

### Authorization

[ApiToken](../../README.md#ApiToken)

### HTTP request headers

- **Content-Type**: `application/json`
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `postMerchants()`

```php
postMerchants($post_merchants_request): \TheLogicStudio\GrailPay\Model\PostMerchants201Response
```

Onboard a new Merchant into the ACH application

This endpoint allows for adding a new Merchant to the GrailPay ACH API Ecosystem.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (Token) authorization: ApiToken
$config = TheLogicStudio\GrailPay\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new TheLogicStudio\GrailPay\Api\UsersApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$post_merchants_request = new \TheLogicStudio\GrailPay\Model\PostMerchantsRequest(); // \TheLogicStudio\GrailPay\Model\PostMerchantsRequest

try {
    $result = $apiInstance->postMerchants($post_merchants_request);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling UsersApi->postMerchants: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **post_merchants_request** | [**\TheLogicStudio\GrailPay\Model\PostMerchantsRequest**](../Model/PostMerchantsRequest.md)|  | |

### Return type

[**\TheLogicStudio\GrailPay\Model\PostMerchants201Response**](../Model/PostMerchants201Response.md)

### Authorization

[ApiToken](../../README.md#ApiToken)

### HTTP request headers

- **Content-Type**: `application/json`
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `postMerchantsByUuidActivate()`

```php
postMerchantsByUuidActivate($uuid): \TheLogicStudio\GrailPay\Model\PostMerchantsByUuidActivate200Response
```

Activate a Merchant

This endpoint allows for activating a Merchant in the GrailPay ACH API Ecosystem. The operation is idempotent: calling it on an already active merchant returns 200 and leaves state unchanged.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (Token) authorization: ApiToken
$config = TheLogicStudio\GrailPay\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new TheLogicStudio\GrailPay\Api\UsersApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$uuid = 7c41f6a2-a4b9-4df8-9225-2c1b7312042e; // string | merchant UUID

try {
    $result = $apiInstance->postMerchantsByUuidActivate($uuid);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling UsersApi->postMerchantsByUuidActivate: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **uuid** | **string**| merchant UUID | |

### Return type

[**\TheLogicStudio\GrailPay\Model\PostMerchantsByUuidActivate200Response**](../Model/PostMerchantsByUuidActivate200Response.md)

### Authorization

[ApiToken](../../README.md#ApiToken)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `postMerchantsByUuidDeactivate()`

```php
postMerchantsByUuidDeactivate($uuid, $post_merchants_by_uuid_deactivate_request): \TheLogicStudio\GrailPay\Model\PostMerchantsByUuidDeactivate200Response
```

Deactivate a Merchant

This endpoint allows for deactivating a Merchant in the GrailPay ACH API Ecosystem. The operation is idempotent: calling it on an already inactive merchant returns 200 and leaves state unchanged.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (Token) authorization: ApiToken
$config = TheLogicStudio\GrailPay\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new TheLogicStudio\GrailPay\Api\UsersApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$uuid = 7c41f6a2-a4b9-4df8-9225-2c1b7312042e; // string | merchant UUID
$post_merchants_by_uuid_deactivate_request = new \TheLogicStudio\GrailPay\Model\PostMerchantsByUuidDeactivateRequest(); // \TheLogicStudio\GrailPay\Model\PostMerchantsByUuidDeactivateRequest

try {
    $result = $apiInstance->postMerchantsByUuidDeactivate($uuid, $post_merchants_by_uuid_deactivate_request);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling UsersApi->postMerchantsByUuidDeactivate: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **uuid** | **string**| merchant UUID | |
| **post_merchants_by_uuid_deactivate_request** | [**\TheLogicStudio\GrailPay\Model\PostMerchantsByUuidDeactivateRequest**](../Model/PostMerchantsByUuidDeactivateRequest.md)|  | [optional] |

### Return type

[**\TheLogicStudio\GrailPay\Model\PostMerchantsByUuidDeactivate200Response**](../Model/PostMerchantsByUuidDeactivate200Response.md)

### Authorization

[ApiToken](../../README.md#ApiToken)

### HTTP request headers

- **Content-Type**: `application/json`
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `postPeople()`

```php
postPeople($post_people_request): \TheLogicStudio\GrailPay\Model\PostPeople201Response
```

Onboard a new Person into the ACH application

This endpoint allows for adding a new Person to the GrailPay ACH API Ecosystem.  The only item that is required is the Bank Account object, but we strongly encourage that you supply as much information as possible.  When including the bank account, you can pass either Plaid information or account and routing information.  You should never pass both.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (Token) authorization: ApiToken
$config = TheLogicStudio\GrailPay\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new TheLogicStudio\GrailPay\Api\UsersApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$post_people_request = new \TheLogicStudio\GrailPay\Model\PostPeopleRequest(); // \TheLogicStudio\GrailPay\Model\PostPeopleRequest

try {
    $result = $apiInstance->postPeople($post_people_request);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling UsersApi->postPeople: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **post_people_request** | [**\TheLogicStudio\GrailPay\Model\PostPeopleRequest**](../Model/PostPeopleRequest.md)|  | |

### Return type

[**\TheLogicStudio\GrailPay\Model\PostPeople201Response**](../Model/PostPeople201Response.md)

### Authorization

[ApiToken](../../README.md#ApiToken)

### HTTP request headers

- **Content-Type**: `application/json`
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `postPeopleKyc()`

```php
postPeopleKyc($post_people_kyc_request): \TheLogicStudio\GrailPay\Model\PostPeopleKyc200Response
```

Register Person KYC

This endpoint registers a person's KYC profile. If matching KYC data already exists, the existing record is returned instead of creating a duplicate.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer (Token) authorization: ApiToken
$config = TheLogicStudio\GrailPay\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new TheLogicStudio\GrailPay\Api\UsersApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$post_people_kyc_request = new \TheLogicStudio\GrailPay\Model\PostPeopleKycRequest(); // \TheLogicStudio\GrailPay\Model\PostPeopleKycRequest

try {
    $result = $apiInstance->postPeopleKyc($post_people_kyc_request);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling UsersApi->postPeopleKyc: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **post_people_kyc_request** | [**\TheLogicStudio\GrailPay\Model\PostPeopleKycRequest**](../Model/PostPeopleKycRequest.md)|  | |

### Return type

[**\TheLogicStudio\GrailPay\Model\PostPeopleKyc200Response**](../Model/PostPeopleKyc200Response.md)

### Authorization

[ApiToken](../../README.md#ApiToken)

### HTTP request headers

- **Content-Type**: `application/json`
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)
