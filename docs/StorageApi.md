# qarax.StorageApi

All URIs are relative to *http://localhost*

Method | HTTP request | Description
------------- | ------------- | -------------
[**add_storage**](StorageApi.md#add_storage) | **POST** /storage | Create new storage
[**get_storage**](StorageApi.md#get_storage) | **GET** /storage/{storageId} | Get storage by ID
[**list_storage**](StorageApi.md#list_storage) | **GET** /storage | Get storage list


# **add_storage**
> CreationResponse add_storage(storage)

Create new storage

Create new storage

### Example


```python
import time
import qarax
from qarax.api import storage_api
from qarax.model.storage import Storage
from qarax.model.error import Error
from qarax.model.creation_response import CreationResponse
from pprint import pprint
# Defining the host is optional and defaults to http://localhost
# See configuration.py for a list of all supported configuration parameters.
configuration = qarax.Configuration(
    host = "http://localhost"
)


# Enter a context with an instance of the API client
with qarax.ApiClient() as api_client:
    # Create an instance of the API class
    api_instance = storage_api.StorageApi(api_client)
    storage = Storage(None) # Storage | 

    # example passing only required values which don't have defaults set
    try:
        # Create new storage
        api_response = api_instance.add_storage(storage)
        pprint(api_response)
    except qarax.ApiException as e:
        print("Exception when calling StorageApi->add_storage: %s\n" % e)
```


### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **storage** | [**Storage**](Storage.md)|  |

### Return type

[**CreationResponse**](CreationResponse.md)

### Authorization

No authorization required

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/json


### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
**200** | successful operation |  -  |
**0** | unexpected error |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **get_storage**
> Storage get_storage(storage_id)

Get storage by ID

### Example


```python
import time
import qarax
from qarax.api import storage_api
from qarax.model.storage import Storage
from qarax.model.error import Error
from pprint import pprint
# Defining the host is optional and defaults to http://localhost
# See configuration.py for a list of all supported configuration parameters.
configuration = qarax.Configuration(
    host = "http://localhost"
)


# Enter a context with an instance of the API client
with qarax.ApiClient() as api_client:
    # Create an instance of the API class
    api_instance = storage_api.StorageApi(api_client)
    storage_id = "storageId_example" # str | ID of storage

    # example passing only required values which don't have defaults set
    try:
        # Get storage by ID
        api_response = api_instance.get_storage(storage_id)
        pprint(api_response)
    except qarax.ApiException as e:
        print("Exception when calling StorageApi->get_storage: %s\n" % e)
```


### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **storage_id** | **str**| ID of storage |

### Return type

[**Storage**](Storage.md)

### Authorization

No authorization required

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json


### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
**200** | successful operation |  -  |
**0** | unexpected error |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **list_storage**
> StorageListResponse list_storage()

Get storage list

Get storage list

### Example


```python
import time
import qarax
from qarax.api import storage_api
from qarax.model.storage_list_response import StorageListResponse
from qarax.model.error import Error
from pprint import pprint
# Defining the host is optional and defaults to http://localhost
# See configuration.py for a list of all supported configuration parameters.
configuration = qarax.Configuration(
    host = "http://localhost"
)


# Enter a context with an instance of the API client
with qarax.ApiClient() as api_client:
    # Create an instance of the API class
    api_instance = storage_api.StorageApi(api_client)

    # example, this endpoint has no required or optional parameters
    try:
        # Get storage list
        api_response = api_instance.list_storage()
        pprint(api_response)
    except qarax.ApiException as e:
        print("Exception when calling StorageApi->list_storage: %s\n" % e)
```


### Parameters
This endpoint does not need any parameter.

### Return type

[**StorageListResponse**](StorageListResponse.md)

### Authorization

No authorization required

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json


### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
**200** | successful operation |  -  |
**0** | unexpected error |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

