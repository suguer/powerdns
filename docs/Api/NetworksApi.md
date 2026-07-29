# OpenAPI\Client\NetworksApi



All URIs are relative to /api/v1, except if the operation defines another base path.

| Method | HTTP request | Description |
| ------------- | ------------- | ------------- |
| [**getNetwork()**](NetworksApi.md#getNetwork) | **GET** /servers/{server_id}/networks/{ip}/{prefixlen} | Return the view associated to the given network |
| [**listNetworks()**](NetworksApi.md#listNetworks) | **GET** /servers/{server_id}/networks | List all registered networks and views in a server |
| [**setNetwork()**](NetworksApi.md#setNetwork) | **PUT** /servers/{server_id}/networks/{ip}/{prefixlen} | Sets the view associated to the given network |


## `getNetwork()`

```php
getNetwork($server_id, $ip, $prefixlen): \OpenAPI\Client\Model\Network
```

Return the view associated to the given network

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure API key authorization: APIKeyHeader
$config = OpenAPI\Client\Configuration::getDefaultConfiguration()->setApiKey('X-API-Key', 'YOUR_API_KEY');
// Uncomment below to setup prefix (e.g. Bearer) for API key, if needed
// $config = OpenAPI\Client\Configuration::getDefaultConfiguration()->setApiKeyPrefix('X-API-Key', 'Bearer');


$apiInstance = new OpenAPI\Client\Api\NetworksApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$server_id = 'server_id_example'; // string | The id of the server to retrieve
$ip = 'ip_example'; // string | The base address of the network
$prefixlen = 'prefixlen_example'; // string | The length of the network prefix

try {
    $result = $apiInstance->getNetwork($server_id, $ip, $prefixlen);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling NetworksApi->getNetwork: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **server_id** | **string**| The id of the server to retrieve | |
| **ip** | **string**| The base address of the network | |
| **prefixlen** | **string**| The length of the network prefix | |

### Return type

[**\OpenAPI\Client\Model\Network**](../Model/Network.md)

### Authorization

[APIKeyHeader](../../README.md#APIKeyHeader)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `listNetworks()`

```php
listNetworks($server_id): \OpenAPI\Client\Model\Networks
```

List all registered networks and views in a server

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure API key authorization: APIKeyHeader
$config = OpenAPI\Client\Configuration::getDefaultConfiguration()->setApiKey('X-API-Key', 'YOUR_API_KEY');
// Uncomment below to setup prefix (e.g. Bearer) for API key, if needed
// $config = OpenAPI\Client\Configuration::getDefaultConfiguration()->setApiKeyPrefix('X-API-Key', 'Bearer');


$apiInstance = new OpenAPI\Client\Api\NetworksApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$server_id = 'server_id_example'; // string | The id of the server to retrieve

try {
    $result = $apiInstance->listNetworks($server_id);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling NetworksApi->listNetworks: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **server_id** | **string**| The id of the server to retrieve | |

### Return type

[**\OpenAPI\Client\Model\Networks**](../Model/Networks.md)

### Authorization

[APIKeyHeader](../../README.md#APIKeyHeader)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `setNetwork()`

```php
setNetwork($server_id, $ip, $prefixlen, $set_network_request)
```

Sets the view associated to the given network

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure API key authorization: APIKeyHeader
$config = OpenAPI\Client\Configuration::getDefaultConfiguration()->setApiKey('X-API-Key', 'YOUR_API_KEY');
// Uncomment below to setup prefix (e.g. Bearer) for API key, if needed
// $config = OpenAPI\Client\Configuration::getDefaultConfiguration()->setApiKeyPrefix('X-API-Key', 'Bearer');


$apiInstance = new OpenAPI\Client\Api\NetworksApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$server_id = 'server_id_example'; // string | The id of the server to retrieve
$ip = 'ip_example'; // string | The base address of the network
$prefixlen = 'prefixlen_example'; // string | The length of the network prefix
$set_network_request = new \OpenAPI\Client\Model\SetNetworkRequest(); // \OpenAPI\Client\Model\SetNetworkRequest

try {
    $apiInstance->setNetwork($server_id, $ip, $prefixlen, $set_network_request);
} catch (Exception $e) {
    echo 'Exception when calling NetworksApi->setNetwork: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **server_id** | **string**| The id of the server to retrieve | |
| **ip** | **string**| The base address of the network | |
| **prefixlen** | **string**| The length of the network prefix | |
| **set_network_request** | [**\OpenAPI\Client\Model\SetNetworkRequest**](../Model/SetNetworkRequest.md)|  | |

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
