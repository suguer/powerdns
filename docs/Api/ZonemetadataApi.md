# OpenAPI\Client\ZonemetadataApi



All URIs are relative to /api/v1, except if the operation defines another base path.

| Method | HTTP request | Description |
| ------------- | ------------- | ------------- |
| [**createMetadata()**](ZonemetadataApi.md#createMetadata) | **POST** /servers/{server_id}/zones/{zone_id}/metadata | Creates a set of metadata entries |
| [**deleteMetadata()**](ZonemetadataApi.md#deleteMetadata) | **DELETE** /servers/{server_id}/zones/{zone_id}/metadata/{metadata_kind} | Delete all items of a single kind of domain metadata. |
| [**getMetadata()**](ZonemetadataApi.md#getMetadata) | **GET** /servers/{server_id}/zones/{zone_id}/metadata/{metadata_kind} | Get the content of a single kind of domain metadata as a Metadata object. |
| [**listMetadata()**](ZonemetadataApi.md#listMetadata) | **GET** /servers/{server_id}/zones/{zone_id}/metadata | Get all the Metadata associated with the zone. |
| [**modifyMetadata()**](ZonemetadataApi.md#modifyMetadata) | **PUT** /servers/{server_id}/zones/{zone_id}/metadata/{metadata_kind} | Replace the content of a single kind of domain metadata. |


## `createMetadata()`

```php
createMetadata($server_id, $zone_id, $metadata)
```

Creates a set of metadata entries

Creates a set of metadata entries of given kind for the zone. Existing metadata entries for the zone with the same kind are not overwritten.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure API key authorization: APIKeyHeader
$config = OpenAPI\Client\Configuration::getDefaultConfiguration()->setApiKey('X-API-Key', 'YOUR_API_KEY');
// Uncomment below to setup prefix (e.g. Bearer) for API key, if needed
// $config = OpenAPI\Client\Configuration::getDefaultConfiguration()->setApiKeyPrefix('X-API-Key', 'Bearer');


$apiInstance = new OpenAPI\Client\Api\ZonemetadataApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$server_id = 'server_id_example'; // string | The id of the server to retrieve
$zone_id = 'zone_id_example'; // string | The id of the zone to retrieve
$metadata = new \OpenAPI\Client\Model\Metadata(); // \OpenAPI\Client\Model\Metadata | Metadata object with list of values to create

try {
    $apiInstance->createMetadata($server_id, $zone_id, $metadata);
} catch (Exception $e) {
    echo 'Exception when calling ZonemetadataApi->createMetadata: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **server_id** | **string**| The id of the server to retrieve | |
| **zone_id** | **string**| The id of the zone to retrieve | |
| **metadata** | [**\OpenAPI\Client\Model\Metadata**](../Model/Metadata.md)| Metadata object with list of values to create | |

### Return type

void (empty response body)

### Authorization

[APIKeyHeader](../../README.md#APIKeyHeader)

### HTTP request headers

- **Content-Type**: `application/json`
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `deleteMetadata()`

```php
deleteMetadata($server_id, $zone_id, $metadata_kind)
```

Delete all items of a single kind of domain metadata.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure API key authorization: APIKeyHeader
$config = OpenAPI\Client\Configuration::getDefaultConfiguration()->setApiKey('X-API-Key', 'YOUR_API_KEY');
// Uncomment below to setup prefix (e.g. Bearer) for API key, if needed
// $config = OpenAPI\Client\Configuration::getDefaultConfiguration()->setApiKeyPrefix('X-API-Key', 'Bearer');


$apiInstance = new OpenAPI\Client\Api\ZonemetadataApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$server_id = 'server_id_example'; // string | The id of the server to retrieve
$zone_id = 'zone_id_example'; // string | The id of the zone to retrieve
$metadata_kind = 'metadata_kind_example'; // string | The kind of metadata

try {
    $apiInstance->deleteMetadata($server_id, $zone_id, $metadata_kind);
} catch (Exception $e) {
    echo 'Exception when calling ZonemetadataApi->deleteMetadata: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **server_id** | **string**| The id of the server to retrieve | |
| **zone_id** | **string**| The id of the zone to retrieve | |
| **metadata_kind** | **string**| The kind of metadata | |

### Return type

void (empty response body)

### Authorization

[APIKeyHeader](../../README.md#APIKeyHeader)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `getMetadata()`

```php
getMetadata($server_id, $zone_id, $metadata_kind): \OpenAPI\Client\Model\Metadata
```

Get the content of a single kind of domain metadata as a Metadata object.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure API key authorization: APIKeyHeader
$config = OpenAPI\Client\Configuration::getDefaultConfiguration()->setApiKey('X-API-Key', 'YOUR_API_KEY');
// Uncomment below to setup prefix (e.g. Bearer) for API key, if needed
// $config = OpenAPI\Client\Configuration::getDefaultConfiguration()->setApiKeyPrefix('X-API-Key', 'Bearer');


$apiInstance = new OpenAPI\Client\Api\ZonemetadataApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$server_id = 'server_id_example'; // string | The id of the server to retrieve
$zone_id = 'zone_id_example'; // string | The id of the zone to retrieve
$metadata_kind = 'metadata_kind_example'; // string | The kind of metadata

try {
    $result = $apiInstance->getMetadata($server_id, $zone_id, $metadata_kind);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling ZonemetadataApi->getMetadata: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **server_id** | **string**| The id of the server to retrieve | |
| **zone_id** | **string**| The id of the zone to retrieve | |
| **metadata_kind** | **string**| The kind of metadata | |

### Return type

[**\OpenAPI\Client\Model\Metadata**](../Model/Metadata.md)

### Authorization

[APIKeyHeader](../../README.md#APIKeyHeader)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `listMetadata()`

```php
listMetadata($server_id, $zone_id): \OpenAPI\Client\Model\Metadata[]
```

Get all the Metadata associated with the zone.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure API key authorization: APIKeyHeader
$config = OpenAPI\Client\Configuration::getDefaultConfiguration()->setApiKey('X-API-Key', 'YOUR_API_KEY');
// Uncomment below to setup prefix (e.g. Bearer) for API key, if needed
// $config = OpenAPI\Client\Configuration::getDefaultConfiguration()->setApiKeyPrefix('X-API-Key', 'Bearer');


$apiInstance = new OpenAPI\Client\Api\ZonemetadataApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$server_id = 'server_id_example'; // string | The id of the server to retrieve
$zone_id = 'zone_id_example'; // string | The id of the zone to retrieve

try {
    $result = $apiInstance->listMetadata($server_id, $zone_id);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling ZonemetadataApi->listMetadata: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **server_id** | **string**| The id of the server to retrieve | |
| **zone_id** | **string**| The id of the zone to retrieve | |

### Return type

[**\OpenAPI\Client\Model\Metadata[]**](../Model/Metadata.md)

### Authorization

[APIKeyHeader](../../README.md#APIKeyHeader)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `modifyMetadata()`

```php
modifyMetadata($server_id, $zone_id, $metadata_kind): \OpenAPI\Client\Model\Metadata
```

Replace the content of a single kind of domain metadata.

Creates a set of metadata entries of given kind for the zone. Existing metadata entries for the zone with the same kind are removed.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure API key authorization: APIKeyHeader
$config = OpenAPI\Client\Configuration::getDefaultConfiguration()->setApiKey('X-API-Key', 'YOUR_API_KEY');
// Uncomment below to setup prefix (e.g. Bearer) for API key, if needed
// $config = OpenAPI\Client\Configuration::getDefaultConfiguration()->setApiKeyPrefix('X-API-Key', 'Bearer');


$apiInstance = new OpenAPI\Client\Api\ZonemetadataApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$server_id = 'server_id_example'; // string | The id of the server to retrieve
$zone_id = 'zone_id_example'; // string | The id of the zone to retrieve
$metadata_kind = 'metadata_kind_example'; // string | The kind of metadata

try {
    $result = $apiInstance->modifyMetadata($server_id, $zone_id, $metadata_kind);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling ZonemetadataApi->modifyMetadata: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **server_id** | **string**| The id of the server to retrieve | |
| **zone_id** | **string**| The id of the zone to retrieve | |
| **metadata_kind** | **string**| The kind of metadata | |

### Return type

[**\OpenAPI\Client\Model\Metadata**](../Model/Metadata.md)

### Authorization

[APIKeyHeader](../../README.md#APIKeyHeader)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)
