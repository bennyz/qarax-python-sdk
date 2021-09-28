# qarax.HostsApi

All URIs are relative to *http://localhost*

Method | HTTP request | Description
------------- | ------------- | -------------
[**add_host**](HostsApi.md#add_host) | **POST** /hosts | Create new host
[**get_host**](HostsApi.md#get_host) | **GET** /hosts/{hostId} | Get host by ID
[**install_host**](HostsApi.md#install_host) | **POST** /hosts/{hostId}/install | Install qarax node on host
[**list_hosts**](HostsApi.md#list_hosts) | **GET** /hosts | Get hosts list


# **add_host**
> CreationResponse add_host(host)

Create new host

Create new host

### Example

```python
import time
import qarax
from qarax.api import hosts_api
from qarax.model.host import Host
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
    api_instance = hosts_api.HostsApi(api_client)
    host = Host(
        address="address_example",
        host_user="host_user_example",
        name="name_example",
        password="password_example",
        port=1,
    ) # Host | 

    # example passing only required values which don't have defaults set
    try:
        # Create new host
        api_response = api_instance.add_host(host)
        pprint(api_response)
    except qarax.ApiException as e:
        print("Exception when calling HostsApi->add_host: %s\n" % e)
```


### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **host** | [**Host**](Host.md)|  |

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

# **get_host**
> Host get_host(host_id)

Get host by ID

### Example

```python
import time
import qarax
from qarax.api import hosts_api
from qarax.model.host import Host
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
    api_instance = hosts_api.HostsApi(api_client)
    host_id = "hostId_example" # str | ID of host

    # example passing only required values which don't have defaults set
    try:
        # Get host by ID
        api_response = api_instance.get_host(host_id)
        pprint(api_response)
    except qarax.ApiException as e:
        print("Exception when calling HostsApi->get_host: %s\n" % e)
```


### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **host_id** | **str**| ID of host |

### Return type

[**Host**](Host.md)

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

# **install_host**
> InstallResponse install_host(host_id)

Install qarax node on host

Install and run qarax-node on host

### Example

```python
import time
import qarax
from qarax.api import hosts_api
from qarax.model.install_response import InstallResponse
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
    api_instance = hosts_api.HostsApi(api_client)
    host_id = "hostId_example" # str | ID of host

    # example passing only required values which don't have defaults set
    try:
        # Install qarax node on host
        api_response = api_instance.install_host(host_id)
        pprint(api_response)
    except qarax.ApiException as e:
        print("Exception when calling HostsApi->install_host: %s\n" % e)
```


### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **host_id** | **str**| ID of host |

### Return type

[**InstallResponse**](InstallResponse.md)

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

# **list_hosts**
> HostList list_hosts()

Get hosts list

Get hosts list

### Example

```python
import time
import qarax
from qarax.api import hosts_api
from qarax.model.error import Error
from qarax.model.host_list import HostList
from pprint import pprint
# Defining the host is optional and defaults to http://localhost
# See configuration.py for a list of all supported configuration parameters.
configuration = qarax.Configuration(
    host = "http://localhost"
)


# Enter a context with an instance of the API client
with qarax.ApiClient() as api_client:
    # Create an instance of the API class
    api_instance = hosts_api.HostsApi(api_client)

    # example, this endpoint has no required or optional parameters
    try:
        # Get hosts list
        api_response = api_instance.list_hosts()
        pprint(api_response)
    except qarax.ApiException as e:
        print("Exception when calling HostsApi->list_hosts: %s\n" % e)
```


### Parameters
This endpoint does not need any parameter.

### Return type

[**HostList**](HostList.md)

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

