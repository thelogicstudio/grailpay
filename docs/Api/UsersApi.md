# TheLogicStudio\GrailPay\UsersApi

API Endpoints used for the onboarding and managing People, Businesses, and Merchants.

All URIs are relative to https://api.grailpay.com, except if the operation defines another base path.

| Method | HTTP request | Description |
| ------------- | ------------- | ------------- |
| [**deleteUsers()**](UsersApi.md#deleteUsers) | **DELETE** /3p/api/v2/users/{uuid} | Deleting a User ( STABLE ) |
| [**getBusinesses()**](UsersApi.md#getBusinesses) | **GET** /api/v3/businesses | Get All Businesses ( STABLE ) |
| [**getMerchants()**](UsersApi.md#getMerchants) | **GET** /api/v3/merchants | Get All Merchants ( STABLE ) |
| [**getPeople()**](UsersApi.md#getPeople) | **GET** /api/v3/people | Get All People ( STABLE ) |
| [**patchBusinesses()**](UsersApi.md#patchBusinesses) | **PATCH** /api/v3/businesses/{uuid} | Update a Business into the ACH application ( STABLE ) |
| [**patchMerchants()**](UsersApi.md#patchMerchants) | **PATCH** /api/v3/merchants/{uuid} | Update a Merchant into the ACH application ( STABLE ) |
| [**patchPeople()**](UsersApi.md#patchPeople) | **PATCH** /api/v3/people/{uuid} | Update a Person into the ACH application ( STABLE ) |
| [**postBusinesses()**](UsersApi.md#postBusinesses) | **POST** /api/v3/businesses | Onboard a new Business into the ACH application ( STABLE ) |
| [**postMerchants()**](UsersApi.md#postMerchants) | **POST** /api/v3/merchants | Onboard a new Merchant into the ACH application ( STABLE ) |
| [**postPeople()**](UsersApi.md#postPeople) | **POST** /api/v3/people | Onboard a new Person into the ACH application ( STABLE ) |


## `deleteUsers()`

```php
deleteUsers($uuid): \TheLogicStudio\GrailPay\Model\DeleteUsers200Response
```

Deleting a User ( STABLE )

This API deletes a specific user from the system based on their unique user UUID.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');



$apiInstance = new TheLogicStudio\GrailPay\Api\UsersApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client()
);
$uuid = 'uuid_example'; // string | User UUID

try {
    $result = $apiInstance->deleteUsers($uuid);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling UsersApi->deleteUsers: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **uuid** | **string**| User UUID | |

### Return type

[**\TheLogicStudio\GrailPay\Model\DeleteUsers200Response**](../Model/DeleteUsers200Response.md)

### Authorization

No authorization required

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

Get All Businesses ( STABLE )

This endpoint provides a comprehensive list of all registered businesses, including essential details. Pagination options are available to efficiently manage large datasets.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');



$apiInstance = new TheLogicStudio\GrailPay\Api\UsersApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client()
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

No authorization required

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

Get All Merchants ( STABLE )

This endpoint provides a comprehensive list of all registered merchants, including essential details. Pagination options are available to efficiently manage large datasets.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');



$apiInstance = new TheLogicStudio\GrailPay\Api\UsersApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client()
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

No authorization required

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

Get All People ( STABLE )

This endpoint provides a comprehensive list of all registered people, including essential details. Pagination options are available to efficiently manage large datasets.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');



$apiInstance = new TheLogicStudio\GrailPay\Api\UsersApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client()
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

No authorization required

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `patchBusinesses()`

```php
patchBusinesses($uuid, $post_businesses_request): \TheLogicStudio\GrailPay\Model\PatchBusinesses200Response
```

Update a Business into the ACH application ( STABLE )

This endpoint allows for updating a Business to the GrailPay ACH API Ecosystem.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');



$apiInstance = new TheLogicStudio\GrailPay\Api\UsersApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client()
);
$uuid = 'uuid_example'; // string
$post_businesses_request = new \TheLogicStudio\GrailPay\Model\PostBusinessesRequest(); // \TheLogicStudio\GrailPay\Model\PostBusinessesRequest

try {
    $result = $apiInstance->patchBusinesses($uuid, $post_businesses_request);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling UsersApi->patchBusinesses: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **uuid** | **string**|  | |
| **post_businesses_request** | [**\TheLogicStudio\GrailPay\Model\PostBusinessesRequest**](../Model/PostBusinessesRequest.md)|  | |

### Return type

[**\TheLogicStudio\GrailPay\Model\PatchBusinesses200Response**](../Model/PatchBusinesses200Response.md)

### Authorization

No authorization required

### HTTP request headers

- **Content-Type**: `application/json`
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `patchMerchants()`

```php
patchMerchants($uuid, $post_merchants_request): \TheLogicStudio\GrailPay\Model\PatchMerchants200Response
```

Update a Merchant into the ACH application ( STABLE )

This endpoint allows for updating a Merchant to the GrailPay ACH API Ecosystem.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');



$apiInstance = new TheLogicStudio\GrailPay\Api\UsersApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client()
);
$uuid = 'uuid_example'; // string
$post_merchants_request = new \TheLogicStudio\GrailPay\Model\PostMerchantsRequest(); // \TheLogicStudio\GrailPay\Model\PostMerchantsRequest

try {
    $result = $apiInstance->patchMerchants($uuid, $post_merchants_request);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling UsersApi->patchMerchants: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **uuid** | **string**|  | |
| **post_merchants_request** | [**\TheLogicStudio\GrailPay\Model\PostMerchantsRequest**](../Model/PostMerchantsRequest.md)|  | |

### Return type

[**\TheLogicStudio\GrailPay\Model\PatchMerchants200Response**](../Model/PatchMerchants200Response.md)

### Authorization

No authorization required

### HTTP request headers

- **Content-Type**: `application/json`
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `patchPeople()`

```php
patchPeople($uuid, $post_people_request): \TheLogicStudio\GrailPay\Model\PatchPeople200Response
```

Update a Person into the ACH application ( STABLE )

This endpoint allows for updating a Person to the GrailPay ACH API Ecosystem.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');



$apiInstance = new TheLogicStudio\GrailPay\Api\UsersApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client()
);
$uuid = 'uuid_example'; // string
$post_people_request = new \TheLogicStudio\GrailPay\Model\PostPeopleRequest(); // \TheLogicStudio\GrailPay\Model\PostPeopleRequest

try {
    $result = $apiInstance->patchPeople($uuid, $post_people_request);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling UsersApi->patchPeople: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **uuid** | **string**|  | |
| **post_people_request** | [**\TheLogicStudio\GrailPay\Model\PostPeopleRequest**](../Model/PostPeopleRequest.md)|  | |

### Return type

[**\TheLogicStudio\GrailPay\Model\PatchPeople200Response**](../Model/PatchPeople200Response.md)

### Authorization

No authorization required

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

Onboard a new Business into the ACH application ( STABLE )

This endpoint allows for adding a new Business to the GrailPay ACH API Ecosystem.  The only item that is required is the Bank Account object, but we strongly encourage that you supply as much information as possible.  When including the bank account, you can pass either Plaid information or account and routing information.  You should never pass both.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');



$apiInstance = new TheLogicStudio\GrailPay\Api\UsersApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client()
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

No authorization required

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

Onboard a new Merchant into the ACH application ( STABLE )

This endpoint allows for adding a new Merchant to the GrailPay ACH API Ecosystem.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');



$apiInstance = new TheLogicStudio\GrailPay\Api\UsersApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client()
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

No authorization required

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

Onboard a new Person into the ACH application ( STABLE )

This endpoint allows for adding a new Person to the GrailPay ACH API Ecosystem.  The only item that is required is the Bank Account object, but we strongly encourage that you supply as much information as possible.  When including the bank account, you can pass either Plaid information or account and routing information.  You should never pass both.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');



$apiInstance = new TheLogicStudio\GrailPay\Api\UsersApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client()
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

No authorization required

### HTTP request headers

- **Content-Type**: `application/json`
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)
