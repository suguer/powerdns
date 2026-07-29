# OpenAPI\Client\ZonecryptokeyApi



All URIs are relative to /api/v1, except if the operation defines another base path.

| Method | HTTP request | Description |
| ------------- | ------------- | ------------- |
| [**createCryptokey()**](ZonecryptokeyApi.md#createCryptokey) | **POST** /servers/{server_id}/zones/{zone_id}/cryptokeys | Creates a Cryptokey |
| [**deleteCryptokey()**](ZonecryptokeyApi.md#deleteCryptokey) | **DELETE** /servers/{server_id}/zones/{zone_id}/cryptokeys/{cryptokey_id} | This method deletes a key specified by cryptokey_id. |
| [**getCryptokey()**](ZonecryptokeyApi.md#getCryptokey) | **GET** /servers/{server_id}/zones/{zone_id}/cryptokeys/{cryptokey_id} | Returns all data about the CryptoKey, including the privatekey. |
| [**listCryptokeys()**](ZonecryptokeyApi.md#listCryptokeys) | **GET** /servers/{server_id}/zones/{zone_id}/cryptokeys | Get all CryptoKeys for a zone, except the privatekey |
| [**modifyCryptokey()**](ZonecryptokeyApi.md#modifyCryptokey) | **PUT** /servers/{server_id}/zones/{zone_id}/cryptokeys/{cryptokey_id} | This method (de)activates a key from zone_name specified by cryptokey_id |


## `createCryptokey()`

```php
createCryptokey($server_id, $zone_id, $cryptokey): \OpenAPI\Client\Model\Cryptokey
```

Creates a Cryptokey

This method adds a new key to a zone. The key can either be generated or imported by supplying the content parameter. if content, bits and algo are null, a key will be generated based on the default-ksk-algorithm and default-ksk-size settings for a KSK and the default-zsk-algorithm and default-zsk-size options for a ZSK.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure API key authorization: APIKeyHeader
$config = OpenAPI\Client\Configuration::getDefaultConfiguration()->setApiKey('X-API-Key', 'YOUR_API_KEY');
// Uncomment below to setup prefix (e.g. Bearer) for API key, if needed
// $config = OpenAPI\Client\Configuration::getDefaultConfiguration()->setApiKeyPrefix('X-API-Key', 'Bearer');


$apiInstance = new OpenAPI\Client\Api\ZonecryptokeyApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$server_id = 'server_id_example'; // string | The id of the server to retrieve
$zone_id = 'zone_id_example'; // string | The id of the zone to retrieve
$cryptokey = new \OpenAPI\Client\Model\Cryptokey(); // \OpenAPI\Client\Model\Cryptokey | Add a Cryptokey

try {
    $result = $apiInstance->createCryptokey($server_id, $zone_id, $cryptokey);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling ZonecryptokeyApi->createCryptokey: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **server_id** | **string**| The id of the server to retrieve | |
| **zone_id** | **string**| The id of the zone to retrieve | |
| **cryptokey** | [**\OpenAPI\Client\Model\Cryptokey**](../Model/Cryptokey.md)| Add a Cryptokey | |

### Return type

[**\OpenAPI\Client\Model\Cryptokey**](../Model/Cryptokey.md)

### Authorization

[APIKeyHeader](../../README.md#APIKeyHeader)

### HTTP request headers

- **Content-Type**: `application/json`
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `deleteCryptokey()`

```php
deleteCryptokey($server_id, $zone_id, $cryptokey_id)
```

This method deletes a key specified by cryptokey_id.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure API key authorization: APIKeyHeader
$config = OpenAPI\Client\Configuration::getDefaultConfiguration()->setApiKey('X-API-Key', 'YOUR_API_KEY');
// Uncomment below to setup prefix (e.g. Bearer) for API key, if needed
// $config = OpenAPI\Client\Configuration::getDefaultConfiguration()->setApiKeyPrefix('X-API-Key', 'Bearer');


$apiInstance = new OpenAPI\Client\Api\ZonecryptokeyApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$server_id = 'server_id_example'; // string | The id of the server to retrieve
$zone_id = 'zone_id_example'; // string | The id of the zone to retrieve
$cryptokey_id = 'cryptokey_id_example'; // string | The id value of the CryptoKey

try {
    $apiInstance->deleteCryptokey($server_id, $zone_id, $cryptokey_id);
} catch (Exception $e) {
    echo 'Exception when calling ZonecryptokeyApi->deleteCryptokey: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **server_id** | **string**| The id of the server to retrieve | |
| **zone_id** | **string**| The id of the zone to retrieve | |
| **cryptokey_id** | **string**| The id value of the CryptoKey | |

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

## `getCryptokey()`

```php
getCryptokey($server_id, $zone_id, $cryptokey_id): \OpenAPI\Client\Model\Cryptokey
```

Returns all data about the CryptoKey, including the privatekey.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure API key authorization: APIKeyHeader
$config = OpenAPI\Client\Configuration::getDefaultConfiguration()->setApiKey('X-API-Key', 'YOUR_API_KEY');
// Uncomment below to setup prefix (e.g. Bearer) for API key, if needed
// $config = OpenAPI\Client\Configuration::getDefaultConfiguration()->setApiKeyPrefix('X-API-Key', 'Bearer');


$apiInstance = new OpenAPI\Client\Api\ZonecryptokeyApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$server_id = 'server_id_example'; // string | The id of the server to retrieve
$zone_id = 'zone_id_example'; // string | The id of the zone to retrieve
$cryptokey_id = 'cryptokey_id_example'; // string | The id value of the CryptoKey

try {
    $result = $apiInstance->getCryptokey($server_id, $zone_id, $cryptokey_id);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling ZonecryptokeyApi->getCryptokey: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **server_id** | **string**| The id of the server to retrieve | |
| **zone_id** | **string**| The id of the zone to retrieve | |
| **cryptokey_id** | **string**| The id value of the CryptoKey | |

### Return type

[**\OpenAPI\Client\Model\Cryptokey**](../Model/Cryptokey.md)

### Authorization

[APIKeyHeader](../../README.md#APIKeyHeader)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `listCryptokeys()`

```php
listCryptokeys($server_id, $zone_id): \OpenAPI\Client\Model\Cryptokey[]
```

Get all CryptoKeys for a zone, except the privatekey

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure API key authorization: APIKeyHeader
$config = OpenAPI\Client\Configuration::getDefaultConfiguration()->setApiKey('X-API-Key', 'YOUR_API_KEY');
// Uncomment below to setup prefix (e.g. Bearer) for API key, if needed
// $config = OpenAPI\Client\Configuration::getDefaultConfiguration()->setApiKeyPrefix('X-API-Key', 'Bearer');


$apiInstance = new OpenAPI\Client\Api\ZonecryptokeyApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$server_id = 'server_id_example'; // string | The id of the server to retrieve
$zone_id = 'zone_id_example'; // string | The id of the zone to retrieve

try {
    $result = $apiInstance->listCryptokeys($server_id, $zone_id);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling ZonecryptokeyApi->listCryptokeys: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **server_id** | **string**| The id of the server to retrieve | |
| **zone_id** | **string**| The id of the zone to retrieve | |

### Return type

[**\OpenAPI\Client\Model\Cryptokey[]**](../Model/Cryptokey.md)

### Authorization

[APIKeyHeader](../../README.md#APIKeyHeader)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `modifyCryptokey()`

```php
modifyCryptokey($server_id, $zone_id, $cryptokey_id)
```

This method (de)activates a key from zone_name specified by cryptokey_id

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure API key authorization: APIKeyHeader
$config = OpenAPI\Client\Configuration::getDefaultConfiguration()->setApiKey('X-API-Key', 'YOUR_API_KEY');
// Uncomment below to setup prefix (e.g. Bearer) for API key, if needed
// $config = OpenAPI\Client\Configuration::getDefaultConfiguration()->setApiKeyPrefix('X-API-Key', 'Bearer');


$apiInstance = new OpenAPI\Client\Api\ZonecryptokeyApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$server_id = 'server_id_example'; // string | The id of the server to retrieve
$zone_id = 'zone_id_example'; // string | The id of the zone to retrieve
$cryptokey_id = 'cryptokey_id_example'; // string | The id value of the CryptoKey

try {
    $apiInstance->modifyCryptokey($server_id, $zone_id, $cryptokey_id);
} catch (Exception $e) {
    echo 'Exception when calling ZonecryptokeyApi->modifyCryptokey: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **server_id** | **string**| The id of the server to retrieve | |
| **zone_id** | **string**| The id of the zone to retrieve | |
| **cryptokey_id** | **string**| The id value of the CryptoKey | |

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
