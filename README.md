# qarax
The API for qarax manager

This Python package is automatically generated by the [OpenAPI Generator](https://openapi-generator.tech) project:

- API version: 0.1.0
- Package version: 1.0.0
- Build package: org.openapitools.codegen.languages.PythonClientCodegen

## Requirements.

Python >=3.6

## Installation & Usage
### pip install

If the python package is hosted on a repository, you can install directly using:

```sh
pip install git+https://github.com/GIT_USER_ID/GIT_REPO_ID.git
```
(you may need to run `pip` with root permission: `sudo pip install git+https://github.com/GIT_USER_ID/GIT_REPO_ID.git`)

Then import the package:
```python
import qarax
```

### Setuptools

Install via [Setuptools](http://pypi.python.org/pypi/setuptools).

```sh
python setup.py install --user
```
(or `sudo python setup.py install` to install the package for all users)

Then import the package:
```python
import qarax
```

## Getting Started

Please follow the [installation procedure](#installation--usage) and then run the following:

```python

import time
import qarax
from pprint import pprint
from qarax.api import hosts_api
from qarax.model.creation_response import CreationResponse
from qarax.model.error import Error
from qarax.model.host import Host
from qarax.model.host_list_response import HostListResponse
from qarax.model.string_response import StringResponse
# Defining the host is optional and defaults to http://localhost
# See configuration.py for a list of all supported configuration parameters.
configuration = qarax.Configuration(
    host = "http://localhost"
)



# Enter a context with an instance of the API client
with qarax.ApiClient(configuration) as api_client:
    # Create an instance of the API class
    api_instance = hosts_api.HostsApi(api_client)
    host = Host(None) # Host | 

    try:
        # Create new host
        api_response = api_instance.add_host(host)
        pprint(api_response)
    except qarax.ApiException as e:
        print("Exception when calling HostsApi->add_host: %s\n" % e)
```

## Documentation for API Endpoints

All URIs are relative to *http://localhost*

Class | Method | HTTP request | Description
------------ | ------------- | ------------- | -------------
*HostsApi* | [**add_host**](docs/HostsApi.md#add_host) | **POST** /hosts | Create new host
*HostsApi* | [**get_host**](docs/HostsApi.md#get_host) | **GET** /hosts/{hostId} | Get host by ID
*HostsApi* | [**healthcheck**](docs/HostsApi.md#healthcheck) | **POST** /hosts/{hostId}/healthcheck | Healthcehck a host
*HostsApi* | [**install_host**](docs/HostsApi.md#install_host) | **POST** /hosts/{hostId}/install | Install qarax node on host
*HostsApi* | [**list_hosts**](docs/HostsApi.md#list_hosts) | **GET** /hosts | Get hosts list
*StorageApi* | [**add_storage**](docs/StorageApi.md#add_storage) | **POST** /storage | Create new storage
*StorageApi* | [**get_storage**](docs/StorageApi.md#get_storage) | **GET** /storage/{storageId} | Get storage by ID
*StorageApi* | [**list_storage**](docs/StorageApi.md#list_storage) | **GET** /storage | Get storage list
*VMsApi* | [**add_vm**](docs/VMsApi.md#add_vm) | **POST** /vms | Create new VM
*VMsApi* | [**get_vm**](docs/VMsApi.md#get_vm) | **GET** /vms/{vmId} | Get VM by ID
*VMsApi* | [**list_vms**](docs/VMsApi.md#list_vms) | **GET** /vms | Get VM list
*VMsApi* | [**start_vm**](docs/VMsApi.md#start_vm) | **POST** /vms/{vmId}/start | Start a VM
*VMsApi* | [**stop_vm**](docs/VMsApi.md#stop_vm) | **POST** /vms/{vmId}/stop | Stop a VM


## Documentation For Models

 - [CreationResponse](docs/CreationResponse.md)
 - [Error](docs/Error.md)
 - [Host](docs/Host.md)
 - [HostListResponse](docs/HostListResponse.md)
 - [Storage](docs/Storage.md)
 - [StorageConfig](docs/StorageConfig.md)
 - [StorageListResponse](docs/StorageListResponse.md)
 - [StringResponse](docs/StringResponse.md)
 - [Vm](docs/Vm.md)


## Documentation For Authorization

 All endpoints do not require authorization.

## Author




## Notes for Large OpenAPI documents
If the OpenAPI document is large, imports in qarax.apis and qarax.models may fail with a
RecursionError indicating the maximum recursion limit has been exceeded. In that case, there are a couple of solutions:

Solution 1:
Use specific imports for apis and models like:
- `from qarax.api.default_api import DefaultApi`
- `from qarax.model.pet import Pet`

Solution 2:
Before importing the package, adjust the maximum recursion limit as shown below:
```
import sys
sys.setrecursionlimit(1500)
import qarax
from qarax.apis import *
from qarax.models import *
```

