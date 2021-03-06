# Swagger\Client\TsigkeyApi

All URIs are relative to *https://localhost/api/v1*

Method | HTTP request | Description
------------- | ------------- | -------------
[**createTSIGKey**](TsigkeyApi.md#createTSIGKey) | **POST** /servers/{server_id}/tsigkeys | Add a TSIG key
[**deleteTSIGKey**](TsigkeyApi.md#deleteTSIGKey) | **DELETE** /servers/{server_id}/tsigkeys/{tsigkey_id} | Delete the TSIGKey with tsigkey_id
[**getTSIGKey**](TsigkeyApi.md#getTSIGKey) | **GET** /servers/{server_id}/tsigkeys/{tsigkey_id} | Get a specific TSIGKeys on the server, including the actual key
[**listTSIGKeys**](TsigkeyApi.md#listTSIGKeys) | **GET** /servers/{server_id}/tsigkeys | Get all TSIGKeys on the server, except the actual key
[**putTSIGKey**](TsigkeyApi.md#putTSIGKey) | **PUT** /servers/{server_id}/tsigkeys/{tsigkey_id} | 


# **createTSIGKey**
> \Swagger\Client\Model\TSIGKey createTSIGKey($server_id, $tsigkey)

Add a TSIG key

This methods add a new TSIGKey. The actual key can be generated by the server or be provided by the client

### Example
```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');

// Configure API key authorization: APIKeyHeader
$config = Swagger\Client\Configuration::getDefaultConfiguration()->setApiKey('X-API-Key', 'YOUR_API_KEY');
// Uncomment below to setup prefix (e.g. Bearer) for API key, if needed
// $config = Swagger\Client\Configuration::getDefaultConfiguration()->setApiKeyPrefix('X-API-Key', 'Bearer');

$apiInstance = new Swagger\Client\Api\TsigkeyApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$server_id = "server_id_example"; // string | The id of the server
$tsigkey = new \Swagger\Client\Model\TSIGKey(); // \Swagger\Client\Model\TSIGKey | The TSIGKey to add

try {
    $result = $apiInstance->createTSIGKey($server_id, $tsigkey);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling TsigkeyApi->createTSIGKey: ', $e->getMessage(), PHP_EOL;
}
?>
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **server_id** | **string**| The id of the server |
 **tsigkey** | [**\Swagger\Client\Model\TSIGKey**](../Model/TSIGKey.md)| The TSIGKey to add |

### Return type

[**\Swagger\Client\Model\TSIGKey**](../Model/TSIGKey.md)

### Authorization

[APIKeyHeader](../../README.md#APIKeyHeader)

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to Model list]](../../README.md#documentation-for-models) [[Back to README]](../../README.md)

# **deleteTSIGKey**
> deleteTSIGKey($server_id, $tsigkey_id)

Delete the TSIGKey with tsigkey_id

### Example
```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');

// Configure API key authorization: APIKeyHeader
$config = Swagger\Client\Configuration::getDefaultConfiguration()->setApiKey('X-API-Key', 'YOUR_API_KEY');
// Uncomment below to setup prefix (e.g. Bearer) for API key, if needed
// $config = Swagger\Client\Configuration::getDefaultConfiguration()->setApiKeyPrefix('X-API-Key', 'Bearer');

$apiInstance = new Swagger\Client\Api\TsigkeyApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$server_id = "server_id_example"; // string | The id of the server to retrieve the key from
$tsigkey_id = "tsigkey_id_example"; // string | The id of the TSIGkey. Should match the \"id\" field in the TSIGKey object

try {
    $apiInstance->deleteTSIGKey($server_id, $tsigkey_id);
} catch (Exception $e) {
    echo 'Exception when calling TsigkeyApi->deleteTSIGKey: ', $e->getMessage(), PHP_EOL;
}
?>
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **server_id** | **string**| The id of the server to retrieve the key from |
 **tsigkey_id** | **string**| The id of the TSIGkey. Should match the \&quot;id\&quot; field in the TSIGKey object |

### Return type

void (empty response body)

### Authorization

[APIKeyHeader](../../README.md#APIKeyHeader)

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to Model list]](../../README.md#documentation-for-models) [[Back to README]](../../README.md)

# **getTSIGKey**
> \Swagger\Client\Model\TSIGKey getTSIGKey($server_id, $tsigkey_id)

Get a specific TSIGKeys on the server, including the actual key

### Example
```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');

// Configure API key authorization: APIKeyHeader
$config = Swagger\Client\Configuration::getDefaultConfiguration()->setApiKey('X-API-Key', 'YOUR_API_KEY');
// Uncomment below to setup prefix (e.g. Bearer) for API key, if needed
// $config = Swagger\Client\Configuration::getDefaultConfiguration()->setApiKeyPrefix('X-API-Key', 'Bearer');

$apiInstance = new Swagger\Client\Api\TsigkeyApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$server_id = "server_id_example"; // string | The id of the server to retrieve the key from
$tsigkey_id = "tsigkey_id_example"; // string | The id of the TSIGkey. Should match the \"id\" field in the TSIGKey object

try {
    $result = $apiInstance->getTSIGKey($server_id, $tsigkey_id);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling TsigkeyApi->getTSIGKey: ', $e->getMessage(), PHP_EOL;
}
?>
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **server_id** | **string**| The id of the server to retrieve the key from |
 **tsigkey_id** | **string**| The id of the TSIGkey. Should match the \&quot;id\&quot; field in the TSIGKey object |

### Return type

[**\Swagger\Client\Model\TSIGKey**](../Model/TSIGKey.md)

### Authorization

[APIKeyHeader](../../README.md#APIKeyHeader)

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to Model list]](../../README.md#documentation-for-models) [[Back to README]](../../README.md)

# **listTSIGKeys**
> \Swagger\Client\Model\TSIGKey[] listTSIGKeys($server_id)

Get all TSIGKeys on the server, except the actual key

### Example
```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');

// Configure API key authorization: APIKeyHeader
$config = Swagger\Client\Configuration::getDefaultConfiguration()->setApiKey('X-API-Key', 'YOUR_API_KEY');
// Uncomment below to setup prefix (e.g. Bearer) for API key, if needed
// $config = Swagger\Client\Configuration::getDefaultConfiguration()->setApiKeyPrefix('X-API-Key', 'Bearer');

$apiInstance = new Swagger\Client\Api\TsigkeyApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$server_id = "server_id_example"; // string | The id of the server

try {
    $result = $apiInstance->listTSIGKeys($server_id);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling TsigkeyApi->listTSIGKeys: ', $e->getMessage(), PHP_EOL;
}
?>
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **server_id** | **string**| The id of the server |

### Return type

[**\Swagger\Client\Model\TSIGKey[]**](../Model/TSIGKey.md)

### Authorization

[APIKeyHeader](../../README.md#APIKeyHeader)

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to Model list]](../../README.md#documentation-for-models) [[Back to README]](../../README.md)

# **putTSIGKey**
> \Swagger\Client\Model\TSIGKey putTSIGKey($server_id, $tsigkey_id, $tsigkey)



The TSIGKey at tsigkey_id can be changed in multiple ways:  * Changing the Name, this will remove the key with tsigkey_id after adding.  * Changing the Algorithm  * Changing the Key  Only the relevant fields have to be provided in the request body.

### Example
```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');

// Configure API key authorization: APIKeyHeader
$config = Swagger\Client\Configuration::getDefaultConfiguration()->setApiKey('X-API-Key', 'YOUR_API_KEY');
// Uncomment below to setup prefix (e.g. Bearer) for API key, if needed
// $config = Swagger\Client\Configuration::getDefaultConfiguration()->setApiKeyPrefix('X-API-Key', 'Bearer');

$apiInstance = new Swagger\Client\Api\TsigkeyApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$server_id = "server_id_example"; // string | The id of the server to retrieve the key from
$tsigkey_id = "tsigkey_id_example"; // string | The id of the TSIGkey. Should match the \"id\" field in the TSIGKey object
$tsigkey = new \Swagger\Client\Model\TSIGKey(); // \Swagger\Client\Model\TSIGKey | A (possibly stripped down) TSIGKey object with the new values

try {
    $result = $apiInstance->putTSIGKey($server_id, $tsigkey_id, $tsigkey);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling TsigkeyApi->putTSIGKey: ', $e->getMessage(), PHP_EOL;
}
?>
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **server_id** | **string**| The id of the server to retrieve the key from |
 **tsigkey_id** | **string**| The id of the TSIGkey. Should match the \&quot;id\&quot; field in the TSIGKey object |
 **tsigkey** | [**\Swagger\Client\Model\TSIGKey**](../Model/TSIGKey.md)| A (possibly stripped down) TSIGKey object with the new values |

### Return type

[**\Swagger\Client\Model\TSIGKey**](../Model/TSIGKey.md)

### Authorization

[APIKeyHeader](../../README.md#APIKeyHeader)

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to Model list]](../../README.md#documentation-for-models) [[Back to README]](../../README.md)

