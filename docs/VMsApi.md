# qarax.VMsApi

All URIs are relative to *http://localhost*

Method | HTTP request | Description
------------- | ------------- | -------------
[**add_vm**](VMsApi.md#add_vm) | **POST** /vms | Create new VM
[**get_vm**](VMsApi.md#get_vm) | **GET** /vms/{vmId} | Get VM by ID
[**list_vms**](VMsApi.md#list_vms) | **GET** /vms | Get VM list
[**start_vm**](VMsApi.md#start_vm) | **POST** /vms/{vmId}/start | Start a VM
[**stop_vm**](VMsApi.md#stop_vm) | **POST** /vms/{vmId}/stop | Stop a VM


# **add_vm**
> CreationResponse add_vm(vm)

Create new VM

Create new VM

### Example

```python
import time
import qarax
from qarax.api import vms_api
from qarax.model.error import Error
from qarax.model.creation_response import CreationResponse
from qarax.model.vm import Vm
from pprint import pprint
# Defining the host is optional and defaults to http://localhost
# See configuration.py for a list of all supported configuration parameters.
configuration = qarax.Configuration(
    host = "http://localhost"
)


# Enter a context with an instance of the API client
with qarax.ApiClient() as api_client:
    # Create an instance of the API class
    api_instance = vms_api.VMsApi(api_client)
    vm = Vm(
        name="name_example",
        host_id="host_id_example",
        vcpu=1,
        memory=1,
        ip_address="ip_address_example",
        mac_address="mac_address_example",
        network_mode="dhcp",
        kernel_parameters="kernel_parameters_example",
        kernel="kernel_example",
    ) # Vm | 

    # example passing only required values which don't have defaults set
    try:
        # Create new VM
        api_response = api_instance.add_vm(vm)
        pprint(api_response)
    except qarax.ApiException as e:
        print("Exception when calling VMsApi->add_vm: %s\n" % e)
```


### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **vm** | [**Vm**](Vm.md)|  |

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

# **get_vm**
> Vm get_vm(vm_id)

Get VM by ID

### Example

```python
import time
import qarax
from qarax.api import vms_api
from qarax.model.error import Error
from qarax.model.vm import Vm
from pprint import pprint
# Defining the host is optional and defaults to http://localhost
# See configuration.py for a list of all supported configuration parameters.
configuration = qarax.Configuration(
    host = "http://localhost"
)


# Enter a context with an instance of the API client
with qarax.ApiClient() as api_client:
    # Create an instance of the API class
    api_instance = vms_api.VMsApi(api_client)
    vm_id = "vmId_example" # str | ID of VN

    # example passing only required values which don't have defaults set
    try:
        # Get VM by ID
        api_response = api_instance.get_vm(vm_id)
        pprint(api_response)
    except qarax.ApiException as e:
        print("Exception when calling VMsApi->get_vm: %s\n" % e)
```


### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **vm_id** | **str**| ID of VN |

### Return type

[**Vm**](Vm.md)

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

# **list_vms**
> [Vm] list_vms()

Get VM list

Get VM list

### Example

```python
import time
import qarax
from qarax.api import vms_api
from qarax.model.error import Error
from qarax.model.vm import Vm
from pprint import pprint
# Defining the host is optional and defaults to http://localhost
# See configuration.py for a list of all supported configuration parameters.
configuration = qarax.Configuration(
    host = "http://localhost"
)


# Enter a context with an instance of the API client
with qarax.ApiClient() as api_client:
    # Create an instance of the API class
    api_instance = vms_api.VMsApi(api_client)

    # example, this endpoint has no required or optional parameters
    try:
        # Get VM list
        api_response = api_instance.list_vms()
        pprint(api_response)
    except qarax.ApiException as e:
        print("Exception when calling VMsApi->list_vms: %s\n" % e)
```


### Parameters
This endpoint does not need any parameter.

### Return type

[**[Vm]**](Vm.md)

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

# **start_vm**
> StringResponse start_vm(vm_id)

Start a VM

Start a VM on an available host

### Example

```python
import time
import qarax
from qarax.api import vms_api
from qarax.model.error import Error
from qarax.model.string_response import StringResponse
from pprint import pprint
# Defining the host is optional and defaults to http://localhost
# See configuration.py for a list of all supported configuration parameters.
configuration = qarax.Configuration(
    host = "http://localhost"
)


# Enter a context with an instance of the API client
with qarax.ApiClient() as api_client:
    # Create an instance of the API class
    api_instance = vms_api.VMsApi(api_client)
    vm_id = "vmId_example" # str | ID of VM

    # example passing only required values which don't have defaults set
    try:
        # Start a VM
        api_response = api_instance.start_vm(vm_id)
        pprint(api_response)
    except qarax.ApiException as e:
        print("Exception when calling VMsApi->start_vm: %s\n" % e)
```


### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **vm_id** | **str**| ID of VM |

### Return type

[**StringResponse**](StringResponse.md)

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

# **stop_vm**
> StringResponse stop_vm(vm_id)

Stop a VM

### Example

```python
import time
import qarax
from qarax.api import vms_api
from qarax.model.error import Error
from qarax.model.string_response import StringResponse
from pprint import pprint
# Defining the host is optional and defaults to http://localhost
# See configuration.py for a list of all supported configuration parameters.
configuration = qarax.Configuration(
    host = "http://localhost"
)


# Enter a context with an instance of the API client
with qarax.ApiClient() as api_client:
    # Create an instance of the API class
    api_instance = vms_api.VMsApi(api_client)
    vm_id = "vmId_example" # str | ID of VM

    # example passing only required values which don't have defaults set
    try:
        # Stop a VM
        api_response = api_instance.stop_vm(vm_id)
        pprint(api_response)
    except qarax.ApiException as e:
        print("Exception when calling VMsApi->stop_vm: %s\n" % e)
```


### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **vm_id** | **str**| ID of VM |

### Return type

[**StringResponse**](StringResponse.md)

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

