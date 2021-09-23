# openapi-client
The API for qarax manager

This Python package is automatically generated by the [OpenAPI Generator](https://openapi-generator.tech) project:

- API version: 0.1.0
- Package version: 1.0.0
- Build package: org.openapitools.codegen.languages.PythonClientCodegen

## Requirements.

Python >= 3.6

## Installation & Usage
### pip install

If the python package is hosted on a repository, you can install directly using:

```sh
pip install git+https://github.com/GIT_USER_ID/GIT_REPO_ID.git
```
(you may need to run `pip` with root permission: `sudo pip install git+https://github.com/GIT_USER_ID/GIT_REPO_ID.git`)

Then import the package:
```python
import openapi_client
```

### Setuptools

Install via [Setuptools](http://pypi.python.org/pypi/setuptools).

```sh
python setup.py install --user
```
(or `sudo python setup.py install` to install the package for all users)

Then import the package:
```python
import openapi_client
```

## Getting Started

Please follow the [installation procedure](#installation--usage) and then run the following:

```python

import time
import openapi_client
from pprint import pprint
from openapi_client.api import hosts_api
from openapi_client.model.creation_response import CreationResponse
from openapi_client.model.error import Error
from openapi_client.model.host import Host
# Defining the host is optional and defaults to http://localhost
# See configuration.py for a list of all supported configuration parameters.
configuration = openapi_client.Configuration(
    host = "http://localhost"
)



# Enter a context with an instance of the API client
with openapi_client.ApiClient(configuration) as api_client:
    # Create an instance of the API class
    api_instance = hosts_api.HostsApi(api_client)
    host = Host(
        address="address_example",
        host_user="host_user_example",
        name="name_example",
        password="password_example",
        port=1,
    ) # Host | 

    try:
        # Create new host
        api_response = api_instance.add_host(host)
        pprint(api_response)
    except openapi_client.ApiException as e:
        print("Exception when calling HostsApi->add_host: %s\n" % e)
```

## Documentation for API Endpoints

All URIs are relative to *http://localhost*

Class | Method | HTTP request | Description
------------ | ------------- | ------------- | -------------
*HostsApi* | [**add_host**](docs/HostsApi.md#add_host) | **POST** /hosts | Create new host
*HostsApi* | [**get_host**](docs/HostsApi.md#get_host) | **GET** /hosts/{hostId} | Get host by ID
*HostsApi* | [**install_host**](docs/HostsApi.md#install_host) | **POST** /hosts/{hostId}/install | Install qarax node on host
*HostsApi* | [**list_hosts**](docs/HostsApi.md#list_hosts) | **GET** /hosts | Get hosts list


## Documentation For Models

 - [CreationResponse](docs/CreationResponse.md)
 - [Error](docs/Error.md)
 - [Host](docs/Host.md)


## Documentation For Authorization

 All endpoints do not require authorization.

## Author




## Notes for Large OpenAPI documents
If the OpenAPI document is large, imports in openapi_client.apis and openapi_client.models may fail with a
RecursionError indicating the maximum recursion limit has been exceeded. In that case, there are a couple of solutions:

Solution 1:
Use specific imports for apis and models like:
- `from openapi_client.api.default_api import DefaultApi`
- `from openapi_client.model.pet import Pet`

Solution 2:
Before importing the package, adjust the maximum recursion limit as shown below:
```
import sys
sys.setrecursionlimit(1500)
import openapi_client
from openapi_client.apis import *
from openapi_client.models import *
```

