# NutanixPrism::DomainManagerApi

All URIs are relative to *https://:9440/api*

| Method | HTTP request | Description |
| ------ | ------------ | ----------- |
| [**create_backup_target**](DomainManagerApi.md#create_backup_target) | **POST** /prism/v4.0/management/domain-managers/{domainManagerExtId}/backup-targets | Create backup target  |
| [**create_domain_manager**](DomainManagerApi.md#create_domain_manager) | **POST** /prism/v4.0/config/domain-managers | Deploy a Prism Central |
| [**create_restore_source**](DomainManagerApi.md#create_restore_source) | **POST** /prism/v4.0/management/restore-sources | Create restore source  |
| [**delete_backup_target_by_id**](DomainManagerApi.md#delete_backup_target_by_id) | **DELETE** /prism/v4.0/management/domain-managers/{domainManagerExtId}/backup-targets/{extId} | Delete backup target  |
| [**delete_restore_source_by_id**](DomainManagerApi.md#delete_restore_source_by_id) | **DELETE** /prism/v4.0/management/restore-sources/{extId} | Delete restore source  |
| [**get_backup_target_by_id**](DomainManagerApi.md#get_backup_target_by_id) | **GET** /prism/v4.0/management/domain-managers/{domainManagerExtId}/backup-targets/{extId} | Fetch backup target  |
| [**get_domain_manager_by_id**](DomainManagerApi.md#get_domain_manager_by_id) | **GET** /prism/v4.0/config/domain-managers/{extId} | Get the requested domain manager (Prism Central) entity |
| [**get_restore_point_by_id**](DomainManagerApi.md#get_restore_point_by_id) | **GET** /prism/v4.0/management/restore-sources/{restoreSourceExtId}/restorable-domain-managers/{restorableDomainManagerExtId}/restore-points/{extId} | Get restore point details  |
| [**get_restore_source_by_id**](DomainManagerApi.md#get_restore_source_by_id) | **GET** /prism/v4.0/management/restore-sources/{extId} | Fetch restore source  |
| [**list_backup_targets**](DomainManagerApi.md#list_backup_targets) | **GET** /prism/v4.0/management/domain-managers/{domainManagerExtId}/backup-targets | List backup targets  |
| [**list_domain_managers**](DomainManagerApi.md#list_domain_managers) | **GET** /prism/v4.0/config/domain-managers | List domain manager (Prism Central) configuration details |
| [**list_restorable_domain_managers**](DomainManagerApi.md#list_restorable_domain_managers) | **GET** /prism/v4.0/management/restore-sources/{restoreSourceExtId}/restorable-domain-managers | List restorable domain managers  |
| [**list_restore_points**](DomainManagerApi.md#list_restore_points) | **GET** /prism/v4.0/management/restore-sources/{restoreSourceExtId}/restorable-domain-managers/{restorableDomainManagerExtId}/restore-points | List restore points  |
| [**register**](DomainManagerApi.md#register) | **POST** /prism/v4.0/management/domain-managers/{extId}/$actions/register | Register a domain manager (Prism Central) to a cluster |
| [**restore**](DomainManagerApi.md#restore) | **POST** /prism/v4.0/management/restore-sources/{restoreSourceExtId}/restorable-domain-managers/{restorableDomainManagerExtId}/restore-points/{extId}/$actions/restore | Restore domain manager  |
| [**unregister**](DomainManagerApi.md#unregister) | **POST** /prism/v4.0/management/domain-managers/{extId}/$actions/unregister | Unregister a registered remote cluster from the local cluster |
| [**update_backup_target_by_id**](DomainManagerApi.md#update_backup_target_by_id) | **PUT** /prism/v4.0/management/domain-managers/{domainManagerExtId}/backup-targets/{extId} | Update backup target  |


## create_backup_target

> <CreateBackupTarget202Response> create_backup_target(domain_manager_ext_id, ntnx_request_id, prism_v40_management_backup_target)

Create backup target 

Creates a cluster or object store as the backup target. For a given Prism Central, there can be up to 3 clusters as backup targets  and 1 object store as backup target. If any cluster or object store is not eligible for backup or  lacks appropriate permissions, the API request will fail.  For object store backup targets, specifying backup policy is mandatory along  with the location of the object store. 

### Examples

```ruby
require 'time'
require 'nutanix_prism'
# setup authorization
NutanixPrism.configure do |config|
  # Configure API key authorization: apiKeyAuthScheme
  config.api_key['X-ntnx-api-key'] = 'YOUR API KEY'
  # Uncomment the following line to set a prefix for the API key, e.g. 'Bearer' (defaults to nil)
  # config.api_key_prefix['X-ntnx-api-key'] = 'Bearer'

  # Configure HTTP basic authorization: basicAuthScheme
  config.username = 'YOUR USERNAME'
  config.password = 'YOUR PASSWORD'
end

api_instance = NutanixPrism::DomainManagerApi.new
domain_manager_ext_id = 'eab17485-f237-4711-8c6d-f2fa40e46389' # String | A unique identifier for the domain manager. 
ntnx_request_id = '3436319d-a869-4221-9ee8-6d69776ab5f1' # String | A unique identifier that is associated with each request. The provided value must be opaque and preferably in Universal Unique Identifier (UUID) format. This identifier is also used as an idempotence token for safely retrying requests in case of network errors. All the supported Nutanix API clients add this auto-generated request identifier to each request. 
prism_v40_management_backup_target = NutanixPrism::PrismV40ManagementBackupTarget.new({location: NutanixPrism::PrismV40ManagementBackupTargetAllOfLocation.new({object_type: 'prism.v4.management.ClusterLocation'})}) # PrismV40ManagementBackupTarget | 

begin
  # Create backup target 
  result = api_instance.create_backup_target(domain_manager_ext_id, ntnx_request_id, prism_v40_management_backup_target)
  p result
rescue NutanixPrism::ApiError => e
  puts "Error when calling DomainManagerApi->create_backup_target: #{e}"
end
```

#### Using the create_backup_target_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<CreateBackupTarget202Response>, Integer, Hash)> create_backup_target_with_http_info(domain_manager_ext_id, ntnx_request_id, prism_v40_management_backup_target)

```ruby
begin
  # Create backup target 
  data, status_code, headers = api_instance.create_backup_target_with_http_info(domain_manager_ext_id, ntnx_request_id, prism_v40_management_backup_target)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <CreateBackupTarget202Response>
rescue NutanixPrism::ApiError => e
  puts "Error when calling DomainManagerApi->create_backup_target_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **domain_manager_ext_id** | **String** | A unique identifier for the domain manager.  |  |
| **ntnx_request_id** | **String** | A unique identifier that is associated with each request. The provided value must be opaque and preferably in Universal Unique Identifier (UUID) format. This identifier is also used as an idempotence token for safely retrying requests in case of network errors. All the supported Nutanix API clients add this auto-generated request identifier to each request.  |  |
| **prism_v40_management_backup_target** | [**PrismV40ManagementBackupTarget**](PrismV40ManagementBackupTarget.md) |  |  |

### Return type

[**CreateBackupTarget202Response**](CreateBackupTarget202Response.md)

### Authorization

[apiKeyAuthScheme](../README.md#apiKeyAuthScheme), [basicAuthScheme](../README.md#basicAuthScheme)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json


## create_domain_manager

> <CreateDomainManager202Response> create_domain_manager(ntnx_request_id, prism_v40_config_domain_manager)

Deploy a Prism Central

Deploys a Prism Central using the provided details. Prism Central Size, Network Config are mandatory fields to deploy Prism Central. The response from this endpoint contains the URL in the task object location header that can be used to track the request status.

### Examples

```ruby
require 'time'
require 'nutanix_prism'
# setup authorization
NutanixPrism.configure do |config|
  # Configure API key authorization: apiKeyAuthScheme
  config.api_key['X-ntnx-api-key'] = 'YOUR API KEY'
  # Uncomment the following line to set a prefix for the API key, e.g. 'Bearer' (defaults to nil)
  # config.api_key_prefix['X-ntnx-api-key'] = 'Bearer'

  # Configure HTTP basic authorization: basicAuthScheme
  config.username = 'YOUR USERNAME'
  config.password = 'YOUR PASSWORD'
end

api_instance = NutanixPrism::DomainManagerApi.new
ntnx_request_id = '2c9e96af-7e91-439d-9480-adedff8f4e64' # String | A unique identifier that is associated with each request. The provided value must be opaque and preferably in Universal Unique Identifier (UUID) format. This identifier is also used as an idempotence token for safely retrying requests in case of network errors. All the supported Nutanix API clients add this auto-generated request identifier to each request. 
prism_v40_config_domain_manager = NutanixPrism::PrismV40ConfigDomainManager.new({config: NutanixPrism::PrismV40ConfigDomainManagerClusterConfig.new({build_info: NutanixPrism::ClustermgmtV40ConfigBuildInfo.new, name: 'pc_nutanix_01', size: NutanixPrism::PrismV40ConfigSize::STARTER}), network: NutanixPrism::PrismV40ConfigDomainManagerNetwork.new({name_servers: [NutanixPrism::CommonV10ConfigIPAddressOrFQDN.new], ntp_servers: [NutanixPrism::CommonV10ConfigIPAddressOrFQDN.new], external_networks: [NutanixPrism::PrismV40ConfigExternalNetwork.new({default_gateway: , subnet_mask: , ip_ranges: [NutanixPrism::CommonV10ConfigIpRange.new], network_ext_id: 'bb63edde-0ea7-4bde-8924-daf7a3ec7717'})]})}) # PrismV40ConfigDomainManager | Request body to deploy a Prism Central.

begin
  # Deploy a Prism Central
  result = api_instance.create_domain_manager(ntnx_request_id, prism_v40_config_domain_manager)
  p result
rescue NutanixPrism::ApiError => e
  puts "Error when calling DomainManagerApi->create_domain_manager: #{e}"
end
```

#### Using the create_domain_manager_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<CreateDomainManager202Response>, Integer, Hash)> create_domain_manager_with_http_info(ntnx_request_id, prism_v40_config_domain_manager)

```ruby
begin
  # Deploy a Prism Central
  data, status_code, headers = api_instance.create_domain_manager_with_http_info(ntnx_request_id, prism_v40_config_domain_manager)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <CreateDomainManager202Response>
rescue NutanixPrism::ApiError => e
  puts "Error when calling DomainManagerApi->create_domain_manager_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **ntnx_request_id** | **String** | A unique identifier that is associated with each request. The provided value must be opaque and preferably in Universal Unique Identifier (UUID) format. This identifier is also used as an idempotence token for safely retrying requests in case of network errors. All the supported Nutanix API clients add this auto-generated request identifier to each request.  |  |
| **prism_v40_config_domain_manager** | [**PrismV40ConfigDomainManager**](PrismV40ConfigDomainManager.md) | Request body to deploy a Prism Central. |  |

### Return type

[**CreateDomainManager202Response**](CreateDomainManager202Response.md)

### Authorization

[apiKeyAuthScheme](../README.md#apiKeyAuthScheme), [basicAuthScheme](../README.md#basicAuthScheme)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json


## create_restore_source

> <CreateRestoreSource201Response> create_restore_source(prism_v40_management_restore_source)

Create restore source 

Creates a restore source pointing to a cluster or object store to restore the domain manager. The created  restore source is intended to be deleted after use. If the restore source is not deleted using the deleteRestoreSource API, then it is auto-deleted after sometime. Also note that a restore  source will not contain a backup policy. It is only used to access the backup data at the location from where  the Prism Central may be restored. Credentials used to access the restore source are not validated at the time  of creation of the restore source. They are validated when the restore source is used to fetch data. 

### Examples

```ruby
require 'time'
require 'nutanix_prism'
# setup authorization
NutanixPrism.configure do |config|
  # Configure API key authorization: apiKeyAuthScheme
  config.api_key['X-ntnx-api-key'] = 'YOUR API KEY'
  # Uncomment the following line to set a prefix for the API key, e.g. 'Bearer' (defaults to nil)
  # config.api_key_prefix['X-ntnx-api-key'] = 'Bearer'

  # Configure HTTP basic authorization: basicAuthScheme
  config.username = 'YOUR USERNAME'
  config.password = 'YOUR PASSWORD'
end

api_instance = NutanixPrism::DomainManagerApi.new
prism_v40_management_restore_source = NutanixPrism::PrismV40ManagementRestoreSource.new({location: NutanixPrism::PrismV40ManagementBackupTargetAllOfLocation.new({object_type: 'prism.v4.management.ClusterLocation'})}) # PrismV40ManagementRestoreSource | 

begin
  # Create restore source 
  result = api_instance.create_restore_source(prism_v40_management_restore_source)
  p result
rescue NutanixPrism::ApiError => e
  puts "Error when calling DomainManagerApi->create_restore_source: #{e}"
end
```

#### Using the create_restore_source_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<CreateRestoreSource201Response>, Integer, Hash)> create_restore_source_with_http_info(prism_v40_management_restore_source)

```ruby
begin
  # Create restore source 
  data, status_code, headers = api_instance.create_restore_source_with_http_info(prism_v40_management_restore_source)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <CreateRestoreSource201Response>
rescue NutanixPrism::ApiError => e
  puts "Error when calling DomainManagerApi->create_restore_source_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **prism_v40_management_restore_source** | [**PrismV40ManagementRestoreSource**](PrismV40ManagementRestoreSource.md) |  |  |

### Return type

[**CreateRestoreSource201Response**](CreateRestoreSource201Response.md)

### Authorization

[apiKeyAuthScheme](../README.md#apiKeyAuthScheme), [basicAuthScheme](../README.md#basicAuthScheme)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json


## delete_backup_target_by_id

> <DeleteBackupTargetById202Response> delete_backup_target_by_id(domain_manager_ext_id, ext_id, if_match, ntnx_request_id)

Delete backup target 

Removes cluster/object store from the backup targets. This will stop the cluster/object store  from backing up Prism Central data. 

### Examples

```ruby
require 'time'
require 'nutanix_prism'
# setup authorization
NutanixPrism.configure do |config|
  # Configure API key authorization: apiKeyAuthScheme
  config.api_key['X-ntnx-api-key'] = 'YOUR API KEY'
  # Uncomment the following line to set a prefix for the API key, e.g. 'Bearer' (defaults to nil)
  # config.api_key_prefix['X-ntnx-api-key'] = 'Bearer'

  # Configure HTTP basic authorization: basicAuthScheme
  config.username = 'YOUR USERNAME'
  config.password = 'YOUR PASSWORD'
end

api_instance = NutanixPrism::DomainManagerApi.new
domain_manager_ext_id = '3207f853-aa28-4c69-95c4-3673a11fe17b' # String | A unique identifier for the domain manager. 
ext_id = '47588c26-bbab-4298-bf0c-22069b7637e5' # String | A globally unique identifier of an instance that is suitable for external consumption. 
if_match = 'if_match_example' # String | The If-Match request header makes the request conditional. When not provided the server will respond with an HTTP 428 (Precondition Required) response code indicating that the server requires the request to be conditional. The server will allow successful completion of PUT and PATCH operations, if the resource matches the ETag value returned to the response of a GET operation. If the conditional does not match, then an HTTP 412 (Precondition Failed) response 
ntnx_request_id = '8a3b29d9-63c4-488a-8662-b5ceaad526d4' # String | A unique identifier that is associated with each request. The provided value must be opaque and preferably in Universal Unique Identifier (UUID) format. This identifier is also used as an idempotence token for safely retrying requests in case of network errors. All the supported Nutanix API clients add this auto-generated request identifier to each request. 

begin
  # Delete backup target 
  result = api_instance.delete_backup_target_by_id(domain_manager_ext_id, ext_id, if_match, ntnx_request_id)
  p result
rescue NutanixPrism::ApiError => e
  puts "Error when calling DomainManagerApi->delete_backup_target_by_id: #{e}"
end
```

#### Using the delete_backup_target_by_id_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<DeleteBackupTargetById202Response>, Integer, Hash)> delete_backup_target_by_id_with_http_info(domain_manager_ext_id, ext_id, if_match, ntnx_request_id)

```ruby
begin
  # Delete backup target 
  data, status_code, headers = api_instance.delete_backup_target_by_id_with_http_info(domain_manager_ext_id, ext_id, if_match, ntnx_request_id)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <DeleteBackupTargetById202Response>
rescue NutanixPrism::ApiError => e
  puts "Error when calling DomainManagerApi->delete_backup_target_by_id_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **domain_manager_ext_id** | **String** | A unique identifier for the domain manager.  |  |
| **ext_id** | **String** | A globally unique identifier of an instance that is suitable for external consumption.  |  |
| **if_match** | **String** | The If-Match request header makes the request conditional. When not provided the server will respond with an HTTP 428 (Precondition Required) response code indicating that the server requires the request to be conditional. The server will allow successful completion of PUT and PATCH operations, if the resource matches the ETag value returned to the response of a GET operation. If the conditional does not match, then an HTTP 412 (Precondition Failed) response  |  |
| **ntnx_request_id** | **String** | A unique identifier that is associated with each request. The provided value must be opaque and preferably in Universal Unique Identifier (UUID) format. This identifier is also used as an idempotence token for safely retrying requests in case of network errors. All the supported Nutanix API clients add this auto-generated request identifier to each request.  |  |

### Return type

[**DeleteBackupTargetById202Response**](DeleteBackupTargetById202Response.md)

### Authorization

[apiKeyAuthScheme](../README.md#apiKeyAuthScheme), [basicAuthScheme](../README.md#basicAuthScheme)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json


## delete_restore_source_by_id

> delete_restore_source_by_id(ext_id, if_match)

Delete restore source 

Deletes a restore source on a cluster/object store. 

### Examples

```ruby
require 'time'
require 'nutanix_prism'
# setup authorization
NutanixPrism.configure do |config|
  # Configure API key authorization: apiKeyAuthScheme
  config.api_key['X-ntnx-api-key'] = 'YOUR API KEY'
  # Uncomment the following line to set a prefix for the API key, e.g. 'Bearer' (defaults to nil)
  # config.api_key_prefix['X-ntnx-api-key'] = 'Bearer'

  # Configure HTTP basic authorization: basicAuthScheme
  config.username = 'YOUR USERNAME'
  config.password = 'YOUR PASSWORD'
end

api_instance = NutanixPrism::DomainManagerApi.new
ext_id = 'e1ab3b67-2f04-47de-b368-632c52969165' # String | A globally unique identifier of an instance that is suitable for external consumption. 
if_match = 'if_match_example' # String | The If-Match request header makes the request conditional. When not provided the server will respond with an HTTP 428 (Precondition Required) response code indicating that the server requires the request to be conditional. The server will allow successful completion of PUT and PATCH operations, if the resource matches the ETag value returned to the response of a GET operation. If the conditional does not match, then an HTTP 412 (Precondition Failed) response 

begin
  # Delete restore source 
  api_instance.delete_restore_source_by_id(ext_id, if_match)
rescue NutanixPrism::ApiError => e
  puts "Error when calling DomainManagerApi->delete_restore_source_by_id: #{e}"
end
```

#### Using the delete_restore_source_by_id_with_http_info variant

This returns an Array which contains the response data (`nil` in this case), status code and headers.

> <Array(nil, Integer, Hash)> delete_restore_source_by_id_with_http_info(ext_id, if_match)

```ruby
begin
  # Delete restore source 
  data, status_code, headers = api_instance.delete_restore_source_by_id_with_http_info(ext_id, if_match)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => nil
rescue NutanixPrism::ApiError => e
  puts "Error when calling DomainManagerApi->delete_restore_source_by_id_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **ext_id** | **String** | A globally unique identifier of an instance that is suitable for external consumption.  |  |
| **if_match** | **String** | The If-Match request header makes the request conditional. When not provided the server will respond with an HTTP 428 (Precondition Required) response code indicating that the server requires the request to be conditional. The server will allow successful completion of PUT and PATCH operations, if the resource matches the ETag value returned to the response of a GET operation. If the conditional does not match, then an HTTP 412 (Precondition Failed) response  |  |

### Return type

nil (empty response body)

### Authorization

[apiKeyAuthScheme](../README.md#apiKeyAuthScheme), [basicAuthScheme](../README.md#basicAuthScheme)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json


## get_backup_target_by_id

> <GetBackupTargetById200Response> get_backup_target_by_id(ext_id, domain_manager_ext_id)

Fetch backup target 

Retrieves the backup targets (cluster or object store) from a domain manager and returns the backup configuration and lastSyncTimestamp parameter to the user. 

### Examples

```ruby
require 'time'
require 'nutanix_prism'
# setup authorization
NutanixPrism.configure do |config|
  # Configure API key authorization: apiKeyAuthScheme
  config.api_key['X-ntnx-api-key'] = 'YOUR API KEY'
  # Uncomment the following line to set a prefix for the API key, e.g. 'Bearer' (defaults to nil)
  # config.api_key_prefix['X-ntnx-api-key'] = 'Bearer'

  # Configure HTTP basic authorization: basicAuthScheme
  config.username = 'YOUR USERNAME'
  config.password = 'YOUR PASSWORD'
end

api_instance = NutanixPrism::DomainManagerApi.new
ext_id = '142d4d54-62dc-44c1-abe2-f75498964142' # String | A globally unique identifier of an instance that is suitable for external consumption. 
domain_manager_ext_id = '8f7c6648-41c1-451d-9bff-af644ad6d517' # String | A unique identifier for the domain manager. 

begin
  # Fetch backup target 
  result = api_instance.get_backup_target_by_id(ext_id, domain_manager_ext_id)
  p result
rescue NutanixPrism::ApiError => e
  puts "Error when calling DomainManagerApi->get_backup_target_by_id: #{e}"
end
```

#### Using the get_backup_target_by_id_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<GetBackupTargetById200Response>, Integer, Hash)> get_backup_target_by_id_with_http_info(ext_id, domain_manager_ext_id)

```ruby
begin
  # Fetch backup target 
  data, status_code, headers = api_instance.get_backup_target_by_id_with_http_info(ext_id, domain_manager_ext_id)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <GetBackupTargetById200Response>
rescue NutanixPrism::ApiError => e
  puts "Error when calling DomainManagerApi->get_backup_target_by_id_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **ext_id** | **String** | A globally unique identifier of an instance that is suitable for external consumption.  |  |
| **domain_manager_ext_id** | **String** | A unique identifier for the domain manager.  |  |

### Return type

[**GetBackupTargetById200Response**](GetBackupTargetById200Response.md)

### Authorization

[apiKeyAuthScheme](../README.md#apiKeyAuthScheme), [basicAuthScheme](../README.md#basicAuthScheme)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json


## get_domain_manager_by_id

> <GetDomainManagerById200Response> get_domain_manager_by_id(ext_id)

Get the requested domain manager (Prism Central) entity

Fetches the attributes associated with the domain manager (Prism Central) resource based on the provided external identifier. It includes attributes like config, network, node and other information such as size, environment and resource specifications.

### Examples

```ruby
require 'time'
require 'nutanix_prism'
# setup authorization
NutanixPrism.configure do |config|
  # Configure API key authorization: apiKeyAuthScheme
  config.api_key['X-ntnx-api-key'] = 'YOUR API KEY'
  # Uncomment the following line to set a prefix for the API key, e.g. 'Bearer' (defaults to nil)
  # config.api_key_prefix['X-ntnx-api-key'] = 'Bearer'

  # Configure HTTP basic authorization: basicAuthScheme
  config.username = 'YOUR USERNAME'
  config.password = 'YOUR PASSWORD'
end

api_instance = NutanixPrism::DomainManagerApi.new
ext_id = 'b2782774-4437-47ee-a15c-d31453137bc9' # String | The external identifier of the domain manager (Prism Central) resource.

begin
  # Get the requested domain manager (Prism Central) entity
  result = api_instance.get_domain_manager_by_id(ext_id)
  p result
rescue NutanixPrism::ApiError => e
  puts "Error when calling DomainManagerApi->get_domain_manager_by_id: #{e}"
end
```

#### Using the get_domain_manager_by_id_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<GetDomainManagerById200Response>, Integer, Hash)> get_domain_manager_by_id_with_http_info(ext_id)

```ruby
begin
  # Get the requested domain manager (Prism Central) entity
  data, status_code, headers = api_instance.get_domain_manager_by_id_with_http_info(ext_id)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <GetDomainManagerById200Response>
rescue NutanixPrism::ApiError => e
  puts "Error when calling DomainManagerApi->get_domain_manager_by_id_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **ext_id** | **String** | The external identifier of the domain manager (Prism Central) resource. |  |

### Return type

[**GetDomainManagerById200Response**](GetDomainManagerById200Response.md)

### Authorization

[apiKeyAuthScheme](../README.md#apiKeyAuthScheme), [basicAuthScheme](../README.md#basicAuthScheme)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json


## get_restore_point_by_id

> <GetRestorePointById200Response> get_restore_point_by_id(restore_source_ext_id, restorable_domain_manager_ext_id, ext_id)

Get restore point details 

Retrieves detailed information about a specific recovery point and provides essential domain manager information stored in the backup, which is required for the restoration process. 

### Examples

```ruby
require 'time'
require 'nutanix_prism'
# setup authorization
NutanixPrism.configure do |config|
  # Configure API key authorization: apiKeyAuthScheme
  config.api_key['X-ntnx-api-key'] = 'YOUR API KEY'
  # Uncomment the following line to set a prefix for the API key, e.g. 'Bearer' (defaults to nil)
  # config.api_key_prefix['X-ntnx-api-key'] = 'Bearer'

  # Configure HTTP basic authorization: basicAuthScheme
  config.username = 'YOUR USERNAME'
  config.password = 'YOUR PASSWORD'
end

api_instance = NutanixPrism::DomainManagerApi.new
restore_source_ext_id = '3fa3cd21-aa7c-49d5-8904-3e9e0c458342' # String | A unique identifier obtained from the restore source API that corresponds to the details provided for the  restore source. 
restorable_domain_manager_ext_id = '0686c5e5-632e-4e6b-8e7d-68d2c1f80ee7' # String | A unique identifier for the domain manager. 
ext_id = 'd939f6b1-ad85-4be5-b5f1-4647a7219294' # String | Restore point ID for the backup created in cluster/object store. 

begin
  # Get restore point details 
  result = api_instance.get_restore_point_by_id(restore_source_ext_id, restorable_domain_manager_ext_id, ext_id)
  p result
rescue NutanixPrism::ApiError => e
  puts "Error when calling DomainManagerApi->get_restore_point_by_id: #{e}"
end
```

#### Using the get_restore_point_by_id_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<GetRestorePointById200Response>, Integer, Hash)> get_restore_point_by_id_with_http_info(restore_source_ext_id, restorable_domain_manager_ext_id, ext_id)

```ruby
begin
  # Get restore point details 
  data, status_code, headers = api_instance.get_restore_point_by_id_with_http_info(restore_source_ext_id, restorable_domain_manager_ext_id, ext_id)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <GetRestorePointById200Response>
rescue NutanixPrism::ApiError => e
  puts "Error when calling DomainManagerApi->get_restore_point_by_id_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **restore_source_ext_id** | **String** | A unique identifier obtained from the restore source API that corresponds to the details provided for the  restore source.  |  |
| **restorable_domain_manager_ext_id** | **String** | A unique identifier for the domain manager.  |  |
| **ext_id** | **String** | Restore point ID for the backup created in cluster/object store.  |  |

### Return type

[**GetRestorePointById200Response**](GetRestorePointById200Response.md)

### Authorization

[apiKeyAuthScheme](../README.md#apiKeyAuthScheme), [basicAuthScheme](../README.md#basicAuthScheme)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json


## get_restore_source_by_id

> <GetRestoreSourceById200Response> get_restore_source_by_id(ext_id)

Fetch restore source 

Retrieves the restore source from the PE cache store and returns the restore source configuration and external identifier to the user. 

### Examples

```ruby
require 'time'
require 'nutanix_prism'
# setup authorization
NutanixPrism.configure do |config|
  # Configure API key authorization: apiKeyAuthScheme
  config.api_key['X-ntnx-api-key'] = 'YOUR API KEY'
  # Uncomment the following line to set a prefix for the API key, e.g. 'Bearer' (defaults to nil)
  # config.api_key_prefix['X-ntnx-api-key'] = 'Bearer'

  # Configure HTTP basic authorization: basicAuthScheme
  config.username = 'YOUR USERNAME'
  config.password = 'YOUR PASSWORD'
end

api_instance = NutanixPrism::DomainManagerApi.new
ext_id = 'e33177d0-57e9-4a15-8022-367dadbc82aa' # String | A globally unique identifier of an instance that is suitable for external consumption. 

begin
  # Fetch restore source 
  result = api_instance.get_restore_source_by_id(ext_id)
  p result
rescue NutanixPrism::ApiError => e
  puts "Error when calling DomainManagerApi->get_restore_source_by_id: #{e}"
end
```

#### Using the get_restore_source_by_id_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<GetRestoreSourceById200Response>, Integer, Hash)> get_restore_source_by_id_with_http_info(ext_id)

```ruby
begin
  # Fetch restore source 
  data, status_code, headers = api_instance.get_restore_source_by_id_with_http_info(ext_id)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <GetRestoreSourceById200Response>
rescue NutanixPrism::ApiError => e
  puts "Error when calling DomainManagerApi->get_restore_source_by_id_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **ext_id** | **String** | A globally unique identifier of an instance that is suitable for external consumption.  |  |

### Return type

[**GetRestoreSourceById200Response**](GetRestoreSourceById200Response.md)

### Authorization

[apiKeyAuthScheme](../README.md#apiKeyAuthScheme), [basicAuthScheme](../README.md#basicAuthScheme)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json


## list_backup_targets

> <ListBackupTargets200Response> list_backup_targets(domain_manager_ext_id)

List backup targets 

Lists backup targets (cluster or object store) configured for a given domain manager. 

### Examples

```ruby
require 'time'
require 'nutanix_prism'
# setup authorization
NutanixPrism.configure do |config|
  # Configure API key authorization: apiKeyAuthScheme
  config.api_key['X-ntnx-api-key'] = 'YOUR API KEY'
  # Uncomment the following line to set a prefix for the API key, e.g. 'Bearer' (defaults to nil)
  # config.api_key_prefix['X-ntnx-api-key'] = 'Bearer'

  # Configure HTTP basic authorization: basicAuthScheme
  config.username = 'YOUR USERNAME'
  config.password = 'YOUR PASSWORD'
end

api_instance = NutanixPrism::DomainManagerApi.new
domain_manager_ext_id = '6acb6cbd-4574-4b8e-b2d8-04019bf52549' # String | A unique identifier for the domain manager. 

begin
  # List backup targets 
  result = api_instance.list_backup_targets(domain_manager_ext_id)
  p result
rescue NutanixPrism::ApiError => e
  puts "Error when calling DomainManagerApi->list_backup_targets: #{e}"
end
```

#### Using the list_backup_targets_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<ListBackupTargets200Response>, Integer, Hash)> list_backup_targets_with_http_info(domain_manager_ext_id)

```ruby
begin
  # List backup targets 
  data, status_code, headers = api_instance.list_backup_targets_with_http_info(domain_manager_ext_id)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <ListBackupTargets200Response>
rescue NutanixPrism::ApiError => e
  puts "Error when calling DomainManagerApi->list_backup_targets_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **domain_manager_ext_id** | **String** | A unique identifier for the domain manager.  |  |

### Return type

[**ListBackupTargets200Response**](ListBackupTargets200Response.md)

### Authorization

[apiKeyAuthScheme](../README.md#apiKeyAuthScheme), [basicAuthScheme](../README.md#basicAuthScheme)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json


## list_domain_managers

> <ListDomainManagers200Response> list_domain_managers(opts)

List domain manager (Prism Central) configuration details

Returns a list of elements representing the domain manager (Prism Central) instance.

### Examples

```ruby
require 'time'
require 'nutanix_prism'
# setup authorization
NutanixPrism.configure do |config|
  # Configure API key authorization: apiKeyAuthScheme
  config.api_key['X-ntnx-api-key'] = 'YOUR API KEY'
  # Uncomment the following line to set a prefix for the API key, e.g. 'Bearer' (defaults to nil)
  # config.api_key_prefix['X-ntnx-api-key'] = 'Bearer'

  # Configure HTTP basic authorization: basicAuthScheme
  config.username = 'YOUR USERNAME'
  config.password = 'YOUR PASSWORD'
end

api_instance = NutanixPrism::DomainManagerApi.new
opts = {
  select: 'select_example' # String | A URL query parameter that allows clients to request a specific set of properties for each entity or complex type. Expression specified with the $select must conform to the [OData V4.01](https://docs.oasis-open.org/odata/odata/v4.01/odata-v4.01-part1-protocol.html) URL conventions. If a $select expression consists of a single select item that is an asterisk (i.e., *), then all properties on the matching resource will be returned. - config - extId 
}

begin
  # List domain manager (Prism Central) configuration details
  result = api_instance.list_domain_managers(opts)
  p result
rescue NutanixPrism::ApiError => e
  puts "Error when calling DomainManagerApi->list_domain_managers: #{e}"
end
```

#### Using the list_domain_managers_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<ListDomainManagers200Response>, Integer, Hash)> list_domain_managers_with_http_info(opts)

```ruby
begin
  # List domain manager (Prism Central) configuration details
  data, status_code, headers = api_instance.list_domain_managers_with_http_info(opts)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <ListDomainManagers200Response>
rescue NutanixPrism::ApiError => e
  puts "Error when calling DomainManagerApi->list_domain_managers_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **select** | **String** | A URL query parameter that allows clients to request a specific set of properties for each entity or complex type. Expression specified with the $select must conform to the [OData V4.01](https://docs.oasis-open.org/odata/odata/v4.01/odata-v4.01-part1-protocol.html) URL conventions. If a $select expression consists of a single select item that is an asterisk (i.e., *), then all properties on the matching resource will be returned. - config - extId  | [optional] |

### Return type

[**ListDomainManagers200Response**](ListDomainManagers200Response.md)

### Authorization

[apiKeyAuthScheme](../README.md#apiKeyAuthScheme), [basicAuthScheme](../README.md#basicAuthScheme)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json


## list_restorable_domain_managers

> <ListRestorableDomainManagers200Response> list_restorable_domain_managers(restore_source_ext_id, opts)

List restorable domain managers 

Lists all the domain managers backed up at the object store/cluster. 

### Examples

```ruby
require 'time'
require 'nutanix_prism'
# setup authorization
NutanixPrism.configure do |config|
  # Configure API key authorization: apiKeyAuthScheme
  config.api_key['X-ntnx-api-key'] = 'YOUR API KEY'
  # Uncomment the following line to set a prefix for the API key, e.g. 'Bearer' (defaults to nil)
  # config.api_key_prefix['X-ntnx-api-key'] = 'Bearer'

  # Configure HTTP basic authorization: basicAuthScheme
  config.username = 'YOUR USERNAME'
  config.password = 'YOUR PASSWORD'
end

api_instance = NutanixPrism::DomainManagerApi.new
restore_source_ext_id = '42fe0ae0-3e6e-4de6-91d9-bf24c6a4b039' # String | A unique identifier obtained from the restore source API that corresponds to the details provided for the  restore source. 
opts = {
  page: 56, # Integer | A URL query parameter that specifies the page number of the result set. It must be a positive integer between 0 and the maximum number of pages that are available for that resource. Any number out of this range might lead to no results. 
  limit: 56, # Integer | A URL query parameter that specifies the total number of records returned in the result set.  Must be a positive integer between 1 and 100. Any number out of this range will lead to a validation error. If the limit is not provided, a default value of 50 records will be returned in the result set. 
  filter: 'filter_example' # String | A URL query parameter that allows clients to filter a collection of resources. The expression specified with $filter is evaluated for each resource in the collection, and only items where the expression evaluates to true are included in the response. Expression specified with the $filter must conform to the [OData V4.01](https://docs.oasis-open.org/odata/odata/v4.01/odata-v4.01-part1-protocol.html) URL conventions. For example, filter '$filter=name eq 'karbon-ntnx-1.0' would filter the result on cluster name 'karbon-ntnx1.0', filter '$filter=startswith(name, 'C')' would filter on cluster name starting with 'C'. The filter can be applied to the following fields: - extId 
}

begin
  # List restorable domain managers 
  result = api_instance.list_restorable_domain_managers(restore_source_ext_id, opts)
  p result
rescue NutanixPrism::ApiError => e
  puts "Error when calling DomainManagerApi->list_restorable_domain_managers: #{e}"
end
```

#### Using the list_restorable_domain_managers_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<ListRestorableDomainManagers200Response>, Integer, Hash)> list_restorable_domain_managers_with_http_info(restore_source_ext_id, opts)

```ruby
begin
  # List restorable domain managers 
  data, status_code, headers = api_instance.list_restorable_domain_managers_with_http_info(restore_source_ext_id, opts)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <ListRestorableDomainManagers200Response>
rescue NutanixPrism::ApiError => e
  puts "Error when calling DomainManagerApi->list_restorable_domain_managers_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **restore_source_ext_id** | **String** | A unique identifier obtained from the restore source API that corresponds to the details provided for the  restore source.  |  |
| **page** | **Integer** | A URL query parameter that specifies the page number of the result set. It must be a positive integer between 0 and the maximum number of pages that are available for that resource. Any number out of this range might lead to no results.  | [optional][default to 0] |
| **limit** | **Integer** | A URL query parameter that specifies the total number of records returned in the result set.  Must be a positive integer between 1 and 100. Any number out of this range will lead to a validation error. If the limit is not provided, a default value of 50 records will be returned in the result set.  | [optional][default to 50] |
| **filter** | **String** | A URL query parameter that allows clients to filter a collection of resources. The expression specified with $filter is evaluated for each resource in the collection, and only items where the expression evaluates to true are included in the response. Expression specified with the $filter must conform to the [OData V4.01](https://docs.oasis-open.org/odata/odata/v4.01/odata-v4.01-part1-protocol.html) URL conventions. For example, filter &#39;$filter&#x3D;name eq &#39;karbon-ntnx-1.0&#39; would filter the result on cluster name &#39;karbon-ntnx1.0&#39;, filter &#39;$filter&#x3D;startswith(name, &#39;C&#39;)&#39; would filter on cluster name starting with &#39;C&#39;. The filter can be applied to the following fields: - extId  | [optional] |

### Return type

[**ListRestorableDomainManagers200Response**](ListRestorableDomainManagers200Response.md)

### Authorization

[apiKeyAuthScheme](../README.md#apiKeyAuthScheme), [basicAuthScheme](../README.md#basicAuthScheme)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json


## list_restore_points

> <ListRestorePoints200Response> list_restore_points(restore_source_ext_id, restorable_domain_manager_ext_id, opts)

List restore points 

The list restore points API allows you to retrieve a list of available restore points,  which are snapshots of the domain manager taken at different times. These restore points can be used to revert the domain manager to a previous state. The list response includes the creation time and identifier ID for the configuration data.<br>  1. For cluster-based backups, only the most recent restore point is available, as backups are continuous.<br> 2. For object store-based backups, multiple restore points may be available, depending on the configured  Recovery Point Objective (RPO) and the retention period set on the s3 bucket. 

### Examples

```ruby
require 'time'
require 'nutanix_prism'
# setup authorization
NutanixPrism.configure do |config|
  # Configure API key authorization: apiKeyAuthScheme
  config.api_key['X-ntnx-api-key'] = 'YOUR API KEY'
  # Uncomment the following line to set a prefix for the API key, e.g. 'Bearer' (defaults to nil)
  # config.api_key_prefix['X-ntnx-api-key'] = 'Bearer'

  # Configure HTTP basic authorization: basicAuthScheme
  config.username = 'YOUR USERNAME'
  config.password = 'YOUR PASSWORD'
end

api_instance = NutanixPrism::DomainManagerApi.new
restore_source_ext_id = '37ef6550-d160-4891-a9a6-6c6650b72879' # String | A unique identifier obtained from the restore source API that corresponds to the details provided for the  restore source. 
restorable_domain_manager_ext_id = '1d7facb6-e399-4ddc-84ef-6c5c8c9445d1' # String | A unique identifier for the domain manager. 
opts = {
  page: 56, # Integer | A URL query parameter that specifies the page number of the result set. It must be a positive integer between 0 and the maximum number of pages that are available for that resource. Any number out of this range might lead to no results. 
  limit: 56, # Integer | A URL query parameter that specifies the total number of records returned in the result set.  Must be a positive integer between 1 and 100. Any number out of this range will lead to a validation error. If the limit is not provided, a default value of 50 records will be returned in the result set. 
  filter: 'filter_example', # String | A URL query parameter that allows clients to filter a collection of resources. The expression specified with $filter is evaluated for each resource in the collection, and only items where the expression evaluates to true are included in the response. Expression specified with the $filter must conform to the [OData V4.01](https://docs.oasis-open.org/odata/odata/v4.01/odata-v4.01-part1-protocol.html) URL conventions. For example, filter '$filter=name eq 'karbon-ntnx-1.0' would filter the result on cluster name 'karbon-ntnx1.0', filter '$filter=startswith(name, 'C')' would filter on cluster name starting with 'C'. The filter can be applied to the following fields: - creationTime 
  orderby: 'orderby_example', # String | A URL query parameter that allows clients to specify the sort criteria for the returned list of objects. Resources can be sorted in ascending order using asc or descending order using desc. If asc or desc are not specified, the resources will be sorted in ascending order by default. For example, '$orderby=templateName desc' would get all templates sorted by templateName in descending order. The orderby can be applied to the following fields: - creationTime 
  select: 'select_example' # String | A URL query parameter that allows clients to request a specific set of properties for each entity or complex type. Expression specified with the $select must conform to the [OData V4.01](https://docs.oasis-open.org/odata/odata/v4.01/odata-v4.01-part1-protocol.html) URL conventions. If a $select expression consists of a single select item that is an asterisk (i.e., *), then all properties on the matching resource will be returned. - creationTime - domainManager - extId - links - tenantId 
}

begin
  # List restore points 
  result = api_instance.list_restore_points(restore_source_ext_id, restorable_domain_manager_ext_id, opts)
  p result
rescue NutanixPrism::ApiError => e
  puts "Error when calling DomainManagerApi->list_restore_points: #{e}"
end
```

#### Using the list_restore_points_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<ListRestorePoints200Response>, Integer, Hash)> list_restore_points_with_http_info(restore_source_ext_id, restorable_domain_manager_ext_id, opts)

```ruby
begin
  # List restore points 
  data, status_code, headers = api_instance.list_restore_points_with_http_info(restore_source_ext_id, restorable_domain_manager_ext_id, opts)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <ListRestorePoints200Response>
rescue NutanixPrism::ApiError => e
  puts "Error when calling DomainManagerApi->list_restore_points_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **restore_source_ext_id** | **String** | A unique identifier obtained from the restore source API that corresponds to the details provided for the  restore source.  |  |
| **restorable_domain_manager_ext_id** | **String** | A unique identifier for the domain manager.  |  |
| **page** | **Integer** | A URL query parameter that specifies the page number of the result set. It must be a positive integer between 0 and the maximum number of pages that are available for that resource. Any number out of this range might lead to no results.  | [optional][default to 0] |
| **limit** | **Integer** | A URL query parameter that specifies the total number of records returned in the result set.  Must be a positive integer between 1 and 100. Any number out of this range will lead to a validation error. If the limit is not provided, a default value of 50 records will be returned in the result set.  | [optional][default to 50] |
| **filter** | **String** | A URL query parameter that allows clients to filter a collection of resources. The expression specified with $filter is evaluated for each resource in the collection, and only items where the expression evaluates to true are included in the response. Expression specified with the $filter must conform to the [OData V4.01](https://docs.oasis-open.org/odata/odata/v4.01/odata-v4.01-part1-protocol.html) URL conventions. For example, filter &#39;$filter&#x3D;name eq &#39;karbon-ntnx-1.0&#39; would filter the result on cluster name &#39;karbon-ntnx1.0&#39;, filter &#39;$filter&#x3D;startswith(name, &#39;C&#39;)&#39; would filter on cluster name starting with &#39;C&#39;. The filter can be applied to the following fields: - creationTime  | [optional] |
| **orderby** | **String** | A URL query parameter that allows clients to specify the sort criteria for the returned list of objects. Resources can be sorted in ascending order using asc or descending order using desc. If asc or desc are not specified, the resources will be sorted in ascending order by default. For example, &#39;$orderby&#x3D;templateName desc&#39; would get all templates sorted by templateName in descending order. The orderby can be applied to the following fields: - creationTime  | [optional] |
| **select** | **String** | A URL query parameter that allows clients to request a specific set of properties for each entity or complex type. Expression specified with the $select must conform to the [OData V4.01](https://docs.oasis-open.org/odata/odata/v4.01/odata-v4.01-part1-protocol.html) URL conventions. If a $select expression consists of a single select item that is an asterisk (i.e., *), then all properties on the matching resource will be returned. - creationTime - domainManager - extId - links - tenantId  | [optional] |

### Return type

[**ListRestorePoints200Response**](ListRestorePoints200Response.md)

### Authorization

[apiKeyAuthScheme](../README.md#apiKeyAuthScheme), [basicAuthScheme](../README.md#basicAuthScheme)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json


## register

> <Register202Response> register(ext_id, if_match, ntnx_request_id, prism_v40_management_cluster_registration_spec)

Register a domain manager (Prism Central) to a cluster

Registers a domain manager (Prism Central) instance to other entities like PE and PC. This process is asynchronous, creating a registration task and returning its UUID.

### Examples

```ruby
require 'time'
require 'nutanix_prism'
# setup authorization
NutanixPrism.configure do |config|
  # Configure API key authorization: apiKeyAuthScheme
  config.api_key['X-ntnx-api-key'] = 'YOUR API KEY'
  # Uncomment the following line to set a prefix for the API key, e.g. 'Bearer' (defaults to nil)
  # config.api_key_prefix['X-ntnx-api-key'] = 'Bearer'

  # Configure HTTP basic authorization: basicAuthScheme
  config.username = 'YOUR USERNAME'
  config.password = 'YOUR PASSWORD'
end

api_instance = NutanixPrism::DomainManagerApi.new
ext_id = '9d78f7ff-55ff-419a-973d-2b291d7d9690' # String | The external identifier of the domain manager (Prism Central) resource.
if_match = 'if_match_example' # String | The If-Match request header makes the request conditional. When not provided the server will respond with an HTTP 428 (Precondition Required) response code indicating that the server requires the request to be conditional. The server will allow successful completion of PUT and PATCH operations, if the resource matches the ETag value returned to the response of a GET operation. If the conditional does not match, then an HTTP 412 (Precondition Failed) response 
ntnx_request_id = '1ee06a44-0fe3-42c7-90b5-688092057b18' # String | A unique identifier that is associated with each request. The provided value must be opaque and preferably in Universal Unique Identifier (UUID) format. This identifier is also used as an idempotence token for safely retrying requests in case of network errors. All the supported Nutanix API clients add this auto-generated request identifier to each request. 
prism_v40_management_cluster_registration_spec = NutanixPrism::PrismV40ManagementClusterRegistrationSpec.new({remote_cluster: NutanixPrism::PrismV40ManagementAOSRemoteClusterSpec.new({remote_cluster: NutanixPrism::PrismV40ManagementRemoteClusterSpec.new({address: NutanixPrism::CommonV10ConfigIPAddressOrFQDN.new, credentials: NutanixPrism::PrismV40ManagementCredentials.new({authentication: NutanixPrism::CommonV10ConfigBasicAuth.new({username: 'test-user', password: '***********'})})})})}) # PrismV40ManagementClusterRegistrationSpec | The registration request consists of the remote cluster details. Credentials must be of domain manager (Prism Central) role.

begin
  # Register a domain manager (Prism Central) to a cluster
  result = api_instance.register(ext_id, if_match, ntnx_request_id, prism_v40_management_cluster_registration_spec)
  p result
rescue NutanixPrism::ApiError => e
  puts "Error when calling DomainManagerApi->register: #{e}"
end
```

#### Using the register_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<Register202Response>, Integer, Hash)> register_with_http_info(ext_id, if_match, ntnx_request_id, prism_v40_management_cluster_registration_spec)

```ruby
begin
  # Register a domain manager (Prism Central) to a cluster
  data, status_code, headers = api_instance.register_with_http_info(ext_id, if_match, ntnx_request_id, prism_v40_management_cluster_registration_spec)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <Register202Response>
rescue NutanixPrism::ApiError => e
  puts "Error when calling DomainManagerApi->register_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **ext_id** | **String** | The external identifier of the domain manager (Prism Central) resource. |  |
| **if_match** | **String** | The If-Match request header makes the request conditional. When not provided the server will respond with an HTTP 428 (Precondition Required) response code indicating that the server requires the request to be conditional. The server will allow successful completion of PUT and PATCH operations, if the resource matches the ETag value returned to the response of a GET operation. If the conditional does not match, then an HTTP 412 (Precondition Failed) response  |  |
| **ntnx_request_id** | **String** | A unique identifier that is associated with each request. The provided value must be opaque and preferably in Universal Unique Identifier (UUID) format. This identifier is also used as an idempotence token for safely retrying requests in case of network errors. All the supported Nutanix API clients add this auto-generated request identifier to each request.  |  |
| **prism_v40_management_cluster_registration_spec** | [**PrismV40ManagementClusterRegistrationSpec**](PrismV40ManagementClusterRegistrationSpec.md) | The registration request consists of the remote cluster details. Credentials must be of domain manager (Prism Central) role. |  |

### Return type

[**Register202Response**](Register202Response.md)

### Authorization

[apiKeyAuthScheme](../README.md#apiKeyAuthScheme), [basicAuthScheme](../README.md#basicAuthScheme)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json


## restore

> <Restore202Response> restore(restore_source_ext_id, restorable_domain_manager_ext_id, ext_id, prism_v40_management_restore_spec)

Restore domain manager 

The restore domain manager is a task-driven operation to restore a domain manager from a cluster or object store  backup location based on the selected restore point. 

### Examples

```ruby
require 'time'
require 'nutanix_prism'
# setup authorization
NutanixPrism.configure do |config|
  # Configure API key authorization: apiKeyAuthScheme
  config.api_key['X-ntnx-api-key'] = 'YOUR API KEY'
  # Uncomment the following line to set a prefix for the API key, e.g. 'Bearer' (defaults to nil)
  # config.api_key_prefix['X-ntnx-api-key'] = 'Bearer'

  # Configure HTTP basic authorization: basicAuthScheme
  config.username = 'YOUR USERNAME'
  config.password = 'YOUR PASSWORD'
end

api_instance = NutanixPrism::DomainManagerApi.new
restore_source_ext_id = '03ad564f-1859-4391-ac52-ed9e299542c1' # String | A unique identifier obtained from the restore source API that corresponds to the details provided for the  restore source. 
restorable_domain_manager_ext_id = '094a06ae-209d-4896-98dc-f6f4cbf33029' # String | A unique identifier for the domain manager. 
ext_id = 'c9623de4-b5ae-472b-ac21-814198c9fb86' # String | Restore point ID for the backup created in cluster/object store. 
prism_v40_management_restore_spec = NutanixPrism::PrismV40ManagementRestoreSpec.new({domain_manager: NutanixPrism::PrismV40ConfigDomainManager.new({config: NutanixPrism::PrismV40ConfigDomainManagerClusterConfig.new({build_info: NutanixPrism::ClustermgmtV40ConfigBuildInfo.new, name: 'pc_nutanix_01', size: NutanixPrism::PrismV40ConfigSize::STARTER}), network: NutanixPrism::PrismV40ConfigDomainManagerNetwork.new({name_servers: [NutanixPrism::CommonV10ConfigIPAddressOrFQDN.new], ntp_servers: [NutanixPrism::CommonV10ConfigIPAddressOrFQDN.new], external_networks: [NutanixPrism::PrismV40ConfigExternalNetwork.new({default_gateway: , subnet_mask: , ip_ranges: [NutanixPrism::CommonV10ConfigIpRange.new], network_ext_id: 'bb63edde-0ea7-4bde-8924-daf7a3ec7717'})]})})}) # PrismV40ManagementRestoreSpec | 

begin
  # Restore domain manager 
  result = api_instance.restore(restore_source_ext_id, restorable_domain_manager_ext_id, ext_id, prism_v40_management_restore_spec)
  p result
rescue NutanixPrism::ApiError => e
  puts "Error when calling DomainManagerApi->restore: #{e}"
end
```

#### Using the restore_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<Restore202Response>, Integer, Hash)> restore_with_http_info(restore_source_ext_id, restorable_domain_manager_ext_id, ext_id, prism_v40_management_restore_spec)

```ruby
begin
  # Restore domain manager 
  data, status_code, headers = api_instance.restore_with_http_info(restore_source_ext_id, restorable_domain_manager_ext_id, ext_id, prism_v40_management_restore_spec)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <Restore202Response>
rescue NutanixPrism::ApiError => e
  puts "Error when calling DomainManagerApi->restore_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **restore_source_ext_id** | **String** | A unique identifier obtained from the restore source API that corresponds to the details provided for the  restore source.  |  |
| **restorable_domain_manager_ext_id** | **String** | A unique identifier for the domain manager.  |  |
| **ext_id** | **String** | Restore point ID for the backup created in cluster/object store.  |  |
| **prism_v40_management_restore_spec** | [**PrismV40ManagementRestoreSpec**](PrismV40ManagementRestoreSpec.md) |  |  |

### Return type

[**Restore202Response**](Restore202Response.md)

### Authorization

[apiKeyAuthScheme](../README.md#apiKeyAuthScheme), [basicAuthScheme](../README.md#basicAuthScheme)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json


## unregister

> <Unregister202Response> unregister(ext_id, if_match, ntnx_request_id, body)

Unregister a registered remote cluster from the local cluster

Unregister a registered remote cluster from the local cluster. This process is asynchronous, creating an unregisteration task and returning its UUID.

### Examples

```ruby
require 'time'
require 'nutanix_prism'
# setup authorization
NutanixPrism.configure do |config|
  # Configure API key authorization: apiKeyAuthScheme
  config.api_key['X-ntnx-api-key'] = 'YOUR API KEY'
  # Uncomment the following line to set a prefix for the API key, e.g. 'Bearer' (defaults to nil)
  # config.api_key_prefix['X-ntnx-api-key'] = 'Bearer'

  # Configure HTTP basic authorization: basicAuthScheme
  config.username = 'YOUR USERNAME'
  config.password = 'YOUR PASSWORD'
end

api_instance = NutanixPrism::DomainManagerApi.new
ext_id = 'ea571e80-da78-41c9-b4f2-39f02e66c5fe' # String | The external identifier of the domain manager (Prism Central) resource.
if_match = 'if_match_example' # String | The If-Match request header makes the request conditional. When not provided the server will respond with an HTTP 428 (Precondition Required) response code indicating that the server requires the request to be conditional. The server will allow successful completion of PUT and PATCH operations, if the resource matches the ETag value returned to the response of a GET operation. If the conditional does not match, then an HTTP 412 (Precondition Failed) response 
ntnx_request_id = '514a2218-04a1-46db-939d-b004b6c28d45' # String | A unique identifier that is associated with each request. The provided value must be opaque and preferably in Universal Unique Identifier (UUID) format. This identifier is also used as an idempotence token for safely retrying requests in case of network errors. All the supported Nutanix API clients add this auto-generated request identifier to each request. 
body = 3.56 # PrismV40ManagementClusterReference | Payload for unregistering a cluster

begin
  # Unregister a registered remote cluster from the local cluster
  result = api_instance.unregister(ext_id, if_match, ntnx_request_id, body)
  p result
rescue NutanixPrism::ApiError => e
  puts "Error when calling DomainManagerApi->unregister: #{e}"
end
```

#### Using the unregister_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<Unregister202Response>, Integer, Hash)> unregister_with_http_info(ext_id, if_match, ntnx_request_id, body)

```ruby
begin
  # Unregister a registered remote cluster from the local cluster
  data, status_code, headers = api_instance.unregister_with_http_info(ext_id, if_match, ntnx_request_id, body)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <Unregister202Response>
rescue NutanixPrism::ApiError => e
  puts "Error when calling DomainManagerApi->unregister_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **ext_id** | **String** | The external identifier of the domain manager (Prism Central) resource. |  |
| **if_match** | **String** | The If-Match request header makes the request conditional. When not provided the server will respond with an HTTP 428 (Precondition Required) response code indicating that the server requires the request to be conditional. The server will allow successful completion of PUT and PATCH operations, if the resource matches the ETag value returned to the response of a GET operation. If the conditional does not match, then an HTTP 412 (Precondition Failed) response  |  |
| **ntnx_request_id** | **String** | A unique identifier that is associated with each request. The provided value must be opaque and preferably in Universal Unique Identifier (UUID) format. This identifier is also used as an idempotence token for safely retrying requests in case of network errors. All the supported Nutanix API clients add this auto-generated request identifier to each request.  |  |
| **body** | **PrismV40ManagementClusterReference** | Payload for unregistering a cluster |  |

### Return type

[**Unregister202Response**](Unregister202Response.md)

### Authorization

[apiKeyAuthScheme](../README.md#apiKeyAuthScheme), [basicAuthScheme](../README.md#basicAuthScheme)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json


## update_backup_target_by_id

> <UpdateBackupTargetById202Response> update_backup_target_by_id(domain_manager_ext_id, ext_id, if_match, ntnx_request_id, prism_v40_management_backup_target)

Update backup target 

Updates the credentials and/or RPO of the given object store. 

### Examples

```ruby
require 'time'
require 'nutanix_prism'
# setup authorization
NutanixPrism.configure do |config|
  # Configure API key authorization: apiKeyAuthScheme
  config.api_key['X-ntnx-api-key'] = 'YOUR API KEY'
  # Uncomment the following line to set a prefix for the API key, e.g. 'Bearer' (defaults to nil)
  # config.api_key_prefix['X-ntnx-api-key'] = 'Bearer'

  # Configure HTTP basic authorization: basicAuthScheme
  config.username = 'YOUR USERNAME'
  config.password = 'YOUR PASSWORD'
end

api_instance = NutanixPrism::DomainManagerApi.new
domain_manager_ext_id = 'a4cf3a8f-eee9-43bb-8f82-283d058176c9' # String | A unique identifier for the domain manager. 
ext_id = '7287aa8f-504a-4ec2-878c-3dfd5da01dec' # String | A globally unique identifier of an instance that is suitable for external consumption. 
if_match = 'if_match_example' # String | The If-Match request header makes the request conditional. When not provided, the server will respond with  an HTTP-428 (Precondition Required) response code indicating that the server requires the request to be conditional. The server will allow the successful completion of PUT and PATCH operations, if the resource matches the ETag value returned to the response of a GET operation. If the conditional does not match, then an HTTP-412 (Precondition Failed) response will be returned.
ntnx_request_id = '4777f3a5-3ece-4503-b0f2-978b535f49c5' # String | A unique identifier that is associated with each request. The provided value must be opaque and preferably in Universal Unique Identifier (UUID) format. This identifier is also used as an idempotence token for safely retrying requests in case of network errors. All the supported Nutanix API clients add this auto-generated request identifier to each request. 
prism_v40_management_backup_target = NutanixPrism::PrismV40ManagementBackupTarget.new({location: NutanixPrism::PrismV40ManagementBackupTargetAllOfLocation.new({object_type: 'prism.v4.management.ClusterLocation'})}) # PrismV40ManagementBackupTarget | 

begin
  # Update backup target 
  result = api_instance.update_backup_target_by_id(domain_manager_ext_id, ext_id, if_match, ntnx_request_id, prism_v40_management_backup_target)
  p result
rescue NutanixPrism::ApiError => e
  puts "Error when calling DomainManagerApi->update_backup_target_by_id: #{e}"
end
```

#### Using the update_backup_target_by_id_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<UpdateBackupTargetById202Response>, Integer, Hash)> update_backup_target_by_id_with_http_info(domain_manager_ext_id, ext_id, if_match, ntnx_request_id, prism_v40_management_backup_target)

```ruby
begin
  # Update backup target 
  data, status_code, headers = api_instance.update_backup_target_by_id_with_http_info(domain_manager_ext_id, ext_id, if_match, ntnx_request_id, prism_v40_management_backup_target)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <UpdateBackupTargetById202Response>
rescue NutanixPrism::ApiError => e
  puts "Error when calling DomainManagerApi->update_backup_target_by_id_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **domain_manager_ext_id** | **String** | A unique identifier for the domain manager.  |  |
| **ext_id** | **String** | A globally unique identifier of an instance that is suitable for external consumption.  |  |
| **if_match** | **String** | The If-Match request header makes the request conditional. When not provided, the server will respond with  an HTTP-428 (Precondition Required) response code indicating that the server requires the request to be conditional. The server will allow the successful completion of PUT and PATCH operations, if the resource matches the ETag value returned to the response of a GET operation. If the conditional does not match, then an HTTP-412 (Precondition Failed) response will be returned. |  |
| **ntnx_request_id** | **String** | A unique identifier that is associated with each request. The provided value must be opaque and preferably in Universal Unique Identifier (UUID) format. This identifier is also used as an idempotence token for safely retrying requests in case of network errors. All the supported Nutanix API clients add this auto-generated request identifier to each request.  |  |
| **prism_v40_management_backup_target** | [**PrismV40ManagementBackupTarget**](PrismV40ManagementBackupTarget.md) |  |  |

### Return type

[**UpdateBackupTargetById202Response**](UpdateBackupTargetById202Response.md)

### Authorization

[apiKeyAuthScheme](../README.md#apiKeyAuthScheme), [basicAuthScheme](../README.md#basicAuthScheme)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json

