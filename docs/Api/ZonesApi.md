# OpenAPI\Client\ZonesApi



All URIs are relative to /api/v1, except if the operation defines another base path.

| Method | HTTP request | Description |
| ------------- | ------------- | ------------- |
| [**axfrExportZone()**](ZonesApi.md#axfrExportZone) | **GET** /servers/{server_id}/zones/{zone_id}/export | Returns the zone in AXFR format. |
| [**axfrRetrieveZone()**](ZonesApi.md#axfrRetrieveZone) | **PUT** /servers/{server_id}/zones/{zone_id}/axfr-retrieve | Retrieve slave zone from its master. |
| [**createZone()**](ZonesApi.md#createZone) | **POST** /servers/{server_id}/zones | Creates a new domain, returns the Zone on creation. |
| [**deleteZone()**](ZonesApi.md#deleteZone) | **DELETE** /servers/{server_id}/zones/{zone_id} | Deletes this zone, all attached metadata and rrsets. |
| [**listZone()**](ZonesApi.md#listZone) | **GET** /servers/{server_id}/zones/{zone_id} | zone managed by a server |
| [**listZones()**](ZonesApi.md#listZones) | **GET** /servers/{server_id}/zones | List all Zones in a server |
| [**notifyZone()**](ZonesApi.md#notifyZone) | **PUT** /servers/{server_id}/zones/{zone_id}/notify | Send a DNS NOTIFY to all slaves. |
| [**patchZone()**](ZonesApi.md#patchZone) | **PATCH** /servers/{server_id}/zones/{zone_id} | Creates/modifies/deletes RRsets present in the payload and their comments. Returns 204 No Content on success. |
| [**putZone()**](ZonesApi.md#putZone) | **PUT** /servers/{server_id}/zones/{zone_id} | Modifies basic zone data. |
| [**rectifyZone()**](ZonesApi.md#rectifyZone) | **PUT** /servers/{server_id}/zones/{zone_id}/rectify | Rectify the zone data. |


## `axfrExportZone()`

```php
axfrExportZone($server_id, $zone_id): string
```

Returns the zone in AXFR format.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure API key authorization: APIKeyHeader
$config = OpenAPI\Client\Configuration::getDefaultConfiguration()->setApiKey('X-API-Key', 'YOUR_API_KEY');
// Uncomment below to setup prefix (e.g. Bearer) for API key, if needed
// $config = OpenAPI\Client\Configuration::getDefaultConfiguration()->setApiKeyPrefix('X-API-Key', 'Bearer');


$apiInstance = new OpenAPI\Client\Api\ZonesApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$server_id = 'server_id_example'; // string | The id of the server to retrieve
$zone_id = 'zone_id_example'; // string | The id of the zone to retrieve

try {
    $result = $apiInstance->axfrExportZone($server_id, $zone_id);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling ZonesApi->axfrExportZone: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **server_id** | **string**| The id of the server to retrieve | |
| **zone_id** | **string**| The id of the zone to retrieve | |

### Return type

**string**

### Authorization

[APIKeyHeader](../../README.md#APIKeyHeader)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `axfrRetrieveZone()`

```php
axfrRetrieveZone($server_id, $zone_id, $axfr_retrieve_zone_request)
```

Retrieve slave zone from its master.

Fails when zone kind is not Slave, or slave is disabled in the configuration. Clients need not send a body, unless they want to specify a particular primary server address to use.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure API key authorization: APIKeyHeader
$config = OpenAPI\Client\Configuration::getDefaultConfiguration()->setApiKey('X-API-Key', 'YOUR_API_KEY');
// Uncomment below to setup prefix (e.g. Bearer) for API key, if needed
// $config = OpenAPI\Client\Configuration::getDefaultConfiguration()->setApiKeyPrefix('X-API-Key', 'Bearer');


$apiInstance = new OpenAPI\Client\Api\ZonesApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$server_id = 'server_id_example'; // string | The id of the server to retrieve
$zone_id = 'zone_id_example'; // string | The id of the zone to retrieve
$axfr_retrieve_zone_request = new \OpenAPI\Client\Model\AxfrRetrieveZoneRequest(); // \OpenAPI\Client\Model\AxfrRetrieveZoneRequest | An optional primary server address to request AXFR from.

try {
    $apiInstance->axfrRetrieveZone($server_id, $zone_id, $axfr_retrieve_zone_request);
} catch (Exception $e) {
    echo 'Exception when calling ZonesApi->axfrRetrieveZone: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **server_id** | **string**| The id of the server to retrieve | |
| **zone_id** | **string**| The id of the zone to retrieve | |
| **axfr_retrieve_zone_request** | [**\OpenAPI\Client\Model\AxfrRetrieveZoneRequest**](../Model/AxfrRetrieveZoneRequest.md)| An optional primary server address to request AXFR from. | [optional] |

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

## `createZone()`

```php
createZone($server_id, $zone, $rrsets): \OpenAPI\Client\Model\Zone
```

Creates a new domain, returns the Zone on creation.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure API key authorization: APIKeyHeader
$config = OpenAPI\Client\Configuration::getDefaultConfiguration()->setApiKey('X-API-Key', 'YOUR_API_KEY');
// Uncomment below to setup prefix (e.g. Bearer) for API key, if needed
// $config = OpenAPI\Client\Configuration::getDefaultConfiguration()->setApiKeyPrefix('X-API-Key', 'Bearer');


$apiInstance = new OpenAPI\Client\Api\ZonesApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$server_id = 'server_id_example'; // string | The id of the server to retrieve
$zone = new \OpenAPI\Client\Model\Zone(); // \OpenAPI\Client\Model\Zone | The zone struct to patch with
$rrsets = true; // bool | “true” (default) or “false”, whether to include the “rrsets” in the response Zone object.

try {
    $result = $apiInstance->createZone($server_id, $zone, $rrsets);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling ZonesApi->createZone: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **server_id** | **string**| The id of the server to retrieve | |
| **zone** | [**\OpenAPI\Client\Model\Zone**](../Model/Zone.md)| The zone struct to patch with | |
| **rrsets** | **bool**| “true” (default) or “false”, whether to include the “rrsets” in the response Zone object. | [optional] [default to true] |

### Return type

[**\OpenAPI\Client\Model\Zone**](../Model/Zone.md)

### Authorization

[APIKeyHeader](../../README.md#APIKeyHeader)

### HTTP request headers

- **Content-Type**: `application/json`
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `deleteZone()`

```php
deleteZone($server_id, $zone_id)
```

Deletes this zone, all attached metadata and rrsets.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure API key authorization: APIKeyHeader
$config = OpenAPI\Client\Configuration::getDefaultConfiguration()->setApiKey('X-API-Key', 'YOUR_API_KEY');
// Uncomment below to setup prefix (e.g. Bearer) for API key, if needed
// $config = OpenAPI\Client\Configuration::getDefaultConfiguration()->setApiKeyPrefix('X-API-Key', 'Bearer');


$apiInstance = new OpenAPI\Client\Api\ZonesApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$server_id = 'server_id_example'; // string | The id of the server to retrieve
$zone_id = 'zone_id_example'; // string | The id of the zone to retrieve

try {
    $apiInstance->deleteZone($server_id, $zone_id);
} catch (Exception $e) {
    echo 'Exception when calling ZonesApi->deleteZone: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **server_id** | **string**| The id of the server to retrieve | |
| **zone_id** | **string**| The id of the zone to retrieve | |

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

## `listZone()`

```php
listZone($server_id, $zone_id, $rrsets, $record_count, $rrset_name, $rrset_type, $include_disabled): \OpenAPI\Client\Model\Zone
```

zone managed by a server

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure API key authorization: APIKeyHeader
$config = OpenAPI\Client\Configuration::getDefaultConfiguration()->setApiKey('X-API-Key', 'YOUR_API_KEY');
// Uncomment below to setup prefix (e.g. Bearer) for API key, if needed
// $config = OpenAPI\Client\Configuration::getDefaultConfiguration()->setApiKeyPrefix('X-API-Key', 'Bearer');


$apiInstance = new OpenAPI\Client\Api\ZonesApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$server_id = 'server_id_example'; // string | The id of the server to retrieve
$zone_id = 'zone_id_example'; // string | The id of the zone to retrieve
$rrsets = true; // bool | “true” (default) or “false”, whether to include the “rrsets” in the response Zone object.
$record_count = false; // bool | “true” or “false” (default), whether to include a count of the records returned in “rrsets” in the response Zone object.
$rrset_name = 'rrset_name_example'; // string | Limit output and/or count to RRsets for this name.
$rrset_type = 'rrset_type_example'; // string | Limit output and/or count to the RRset of this type. Can only be used together with rrset_name.
$include_disabled = true; // bool | “true” (default) or “false”, whether to include disabled RRsets in the response.

try {
    $result = $apiInstance->listZone($server_id, $zone_id, $rrsets, $record_count, $rrset_name, $rrset_type, $include_disabled);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling ZonesApi->listZone: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **server_id** | **string**| The id of the server to retrieve | |
| **zone_id** | **string**| The id of the zone to retrieve | |
| **rrsets** | **bool**| “true” (default) or “false”, whether to include the “rrsets” in the response Zone object. | [optional] [default to true] |
| **record_count** | **bool**| “true” or “false” (default), whether to include a count of the records returned in “rrsets” in the response Zone object. | [optional] [default to false] |
| **rrset_name** | **string**| Limit output and/or count to RRsets for this name. | [optional] |
| **rrset_type** | **string**| Limit output and/or count to the RRset of this type. Can only be used together with rrset_name. | [optional] |
| **include_disabled** | **bool**| “true” (default) or “false”, whether to include disabled RRsets in the response. | [optional] [default to true] |

### Return type

[**\OpenAPI\Client\Model\Zone**](../Model/Zone.md)

### Authorization

[APIKeyHeader](../../README.md#APIKeyHeader)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `listZones()`

```php
listZones($server_id, $zone, $dnssec): \OpenAPI\Client\Model\Zone[]
```

List all Zones in a server

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure API key authorization: APIKeyHeader
$config = OpenAPI\Client\Configuration::getDefaultConfiguration()->setApiKey('X-API-Key', 'YOUR_API_KEY');
// Uncomment below to setup prefix (e.g. Bearer) for API key, if needed
// $config = OpenAPI\Client\Configuration::getDefaultConfiguration()->setApiKeyPrefix('X-API-Key', 'Bearer');


$apiInstance = new OpenAPI\Client\Api\ZonesApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$server_id = 'server_id_example'; // string | The id of the server to retrieve
$zone = 'zone_example'; // string | When set to the name of a zone, only this zone is returned. If no zone with that name exists, the response is an empty array. This can e.g. be used to check if a zone exists in the database without having to guess/encode the zone's id or to check if a zone exists.
$dnssec = true; // bool | “true” (default) or “false”, whether to include the “dnssec” and “edited_serial” fields in the Zone objects. Setting this to ”false” will make the query a lot faster.

try {
    $result = $apiInstance->listZones($server_id, $zone, $dnssec);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling ZonesApi->listZones: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **server_id** | **string**| The id of the server to retrieve | |
| **zone** | **string**| When set to the name of a zone, only this zone is returned. If no zone with that name exists, the response is an empty array. This can e.g. be used to check if a zone exists in the database without having to guess/encode the zone&#39;s id or to check if a zone exists. | [optional] |
| **dnssec** | **bool**| “true” (default) or “false”, whether to include the “dnssec” and “edited_serial” fields in the Zone objects. Setting this to ”false” will make the query a lot faster. | [optional] [default to true] |

### Return type

[**\OpenAPI\Client\Model\Zone[]**](../Model/Zone.md)

### Authorization

[APIKeyHeader](../../README.md#APIKeyHeader)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `notifyZone()`

```php
notifyZone($server_id, $zone_id)
```

Send a DNS NOTIFY to all slaves.

Fails when zone kind is not Master or Slave, or master and slave are disabled in the configuration. Only works for Slave if renotify is on. Clients MUST NOT send a body.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure API key authorization: APIKeyHeader
$config = OpenAPI\Client\Configuration::getDefaultConfiguration()->setApiKey('X-API-Key', 'YOUR_API_KEY');
// Uncomment below to setup prefix (e.g. Bearer) for API key, if needed
// $config = OpenAPI\Client\Configuration::getDefaultConfiguration()->setApiKeyPrefix('X-API-Key', 'Bearer');


$apiInstance = new OpenAPI\Client\Api\ZonesApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$server_id = 'server_id_example'; // string | The id of the server to retrieve
$zone_id = 'zone_id_example'; // string | The id of the zone to retrieve

try {
    $apiInstance->notifyZone($server_id, $zone_id);
} catch (Exception $e) {
    echo 'Exception when calling ZonesApi->notifyZone: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **server_id** | **string**| The id of the server to retrieve | |
| **zone_id** | **string**| The id of the zone to retrieve | |

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

## `patchZone()`

```php
patchZone($server_id, $zone_id, $zone)
```

Creates/modifies/deletes RRsets present in the payload and their comments. Returns 204 No Content on success.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure API key authorization: APIKeyHeader
$config = OpenAPI\Client\Configuration::getDefaultConfiguration()->setApiKey('X-API-Key', 'YOUR_API_KEY');
// Uncomment below to setup prefix (e.g. Bearer) for API key, if needed
// $config = OpenAPI\Client\Configuration::getDefaultConfiguration()->setApiKeyPrefix('X-API-Key', 'Bearer');


$apiInstance = new OpenAPI\Client\Api\ZonesApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$server_id = 'server_id_example'; // string | The id of the server to retrieve
$zone_id = 'zone_id_example'; // string | The id of the zone to retrieve
$zone = new \OpenAPI\Client\Model\Zone(); // \OpenAPI\Client\Model\Zone | The zone struct to patch with

try {
    $apiInstance->patchZone($server_id, $zone_id, $zone);
} catch (Exception $e) {
    echo 'Exception when calling ZonesApi->patchZone: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **server_id** | **string**| The id of the server to retrieve | |
| **zone_id** | **string**| The id of the zone to retrieve | |
| **zone** | [**\OpenAPI\Client\Model\Zone**](../Model/Zone.md)| The zone struct to patch with | |

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

## `putZone()`

```php
putZone($server_id, $zone_id, $zone)
```

Modifies basic zone data.

The only fields in the zone structure which can be modified are: kind, masters, catalog, account, soa_edit, soa_edit_api, api_rectify, dnssec, and nsec3param. All other fields are ignored.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure API key authorization: APIKeyHeader
$config = OpenAPI\Client\Configuration::getDefaultConfiguration()->setApiKey('X-API-Key', 'YOUR_API_KEY');
// Uncomment below to setup prefix (e.g. Bearer) for API key, if needed
// $config = OpenAPI\Client\Configuration::getDefaultConfiguration()->setApiKeyPrefix('X-API-Key', 'Bearer');


$apiInstance = new OpenAPI\Client\Api\ZonesApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$server_id = 'server_id_example'; // string | The id of the server to retrieve
$zone_id = 'zone_id_example'; // string | The id of the zone to retrieve
$zone = new \OpenAPI\Client\Model\Zone(); // \OpenAPI\Client\Model\Zone | The zone struct to patch with

try {
    $apiInstance->putZone($server_id, $zone_id, $zone);
} catch (Exception $e) {
    echo 'Exception when calling ZonesApi->putZone: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **server_id** | **string**| The id of the server to retrieve | |
| **zone_id** | **string**| The id of the zone to retrieve | |
| **zone** | [**\OpenAPI\Client\Model\Zone**](../Model/Zone.md)| The zone struct to patch with | |

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

## `rectifyZone()`

```php
rectifyZone($server_id, $zone_id): string
```

Rectify the zone data.

This does not take into account the API-RECTIFY metadata. Fails on slave zones and zones that do not have DNSSEC.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure API key authorization: APIKeyHeader
$config = OpenAPI\Client\Configuration::getDefaultConfiguration()->setApiKey('X-API-Key', 'YOUR_API_KEY');
// Uncomment below to setup prefix (e.g. Bearer) for API key, if needed
// $config = OpenAPI\Client\Configuration::getDefaultConfiguration()->setApiKeyPrefix('X-API-Key', 'Bearer');


$apiInstance = new OpenAPI\Client\Api\ZonesApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$server_id = 'server_id_example'; // string | The id of the server to retrieve
$zone_id = 'zone_id_example'; // string | The id of the zone to retrieve

try {
    $result = $apiInstance->rectifyZone($server_id, $zone_id);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling ZonesApi->rectifyZone: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **server_id** | **string**| The id of the server to retrieve | |
| **zone_id** | **string**| The id of the zone to retrieve | |

### Return type

**string**

### Authorization

[APIKeyHeader](../../README.md#APIKeyHeader)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)
