# NutanixPrism::TasksApi

All URIs are relative to *https://:9440/api*

| Method | HTTP request | Description |
| ------ | ------------ | ----------- |
| [**cancel_task**](TasksApi.md#cancel_task) | **POST** /prism/v4.0/config/tasks/{taskExtId}/$actions/cancel | Cancel an ongoing task |
| [**get_task_by_id**](TasksApi.md#get_task_by_id) | **GET** /prism/v4.0/config/tasks/{extId} | Fetch a task |
| [**list_tasks**](TasksApi.md#list_tasks) | **GET** /prism/v4.0/config/tasks | List tasks |


## cancel_task

> <CancelTask200Response> cancel_task(task_ext_id)

Cancel an ongoing task

Cancel an ongoing task for the provided taskExtId. This action is supported only if 'isCancelable' is set as True for the task. The task may continue to run for some time after the request has been made, until the backend server deems it is safe to cancel the task. Cancellation requests are idempotent and multiple such requests for the same ongoing task are supported.

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

api_instance = NutanixPrism::TasksApi.new
task_ext_id = 'QmFzZTY0RW5jb2RlZA==:df8686eb-075d-4772-bfd2-96c5d5003443' # String | A globally unique identifier of a task. It consists of a prefix and a UUID separated by ':'. 'legacy' prefix can be used with a task UUID provided by previous API families.

begin
  # Cancel an ongoing task
  result = api_instance.cancel_task(task_ext_id)
  p result
rescue NutanixPrism::ApiError => e
  puts "Error when calling TasksApi->cancel_task: #{e}"
end
```

#### Using the cancel_task_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<CancelTask200Response>, Integer, Hash)> cancel_task_with_http_info(task_ext_id)

```ruby
begin
  # Cancel an ongoing task
  data, status_code, headers = api_instance.cancel_task_with_http_info(task_ext_id)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <CancelTask200Response>
rescue NutanixPrism::ApiError => e
  puts "Error when calling TasksApi->cancel_task_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **task_ext_id** | **String** | A globally unique identifier of a task. It consists of a prefix and a UUID separated by &#39;:&#39;. &#39;legacy&#39; prefix can be used with a task UUID provided by previous API families. |  |

### Return type

[**CancelTask200Response**](CancelTask200Response.md)

### Authorization

[apiKeyAuthScheme](../README.md#apiKeyAuthScheme), [basicAuthScheme](../README.md#basicAuthScheme)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json


## get_task_by_id

> <GetTaskById200Response> get_task_by_id(ext_id, opts)

Fetch a task

Fetch an asynchronous operation called a task for the provided extId.

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

api_instance = NutanixPrism::TasksApi.new
ext_id = 'QmFzZTY0RW5jb2RlZA==:f1aee1aa-666a-4c56-bb5e-9a01697798e8' # String | A globally unique identifier of a task. It consists of a prefix and a UUID separated by ':'. 'legacy' prefix can be used with a task UUID provided by previous API families.
opts = {
  select: 'select_example' # String | A URL query parameter that allows clients to request a specific set of properties for each entity or complex type. Expression specified with the $select must conform to the [OData V4.01](https://docs.oasis-open.org/odata/odata/v4.01/odata-v4.01-part1-protocol.html) URL conventions. If a $select expression consists of a single select item that is an asterisk (i.e., *), then all properties on the matching resource will be returned. - clusterExtIds - completedTime - completionDetails - createdTime - entitiesAffected - errorMessages - extId - isBackgroundTask - isCancelable - lastUpdatedTime - numberOfEntitiesAffected - numberOfSubtasks - operation - operationDescription - ownedBy/extId - ownedBy/name - parentTask - progressPercentage - rootTask - startedTime - status - subTasks - warnings 
}

begin
  # Fetch a task
  result = api_instance.get_task_by_id(ext_id, opts)
  p result
rescue NutanixPrism::ApiError => e
  puts "Error when calling TasksApi->get_task_by_id: #{e}"
end
```

#### Using the get_task_by_id_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<GetTaskById200Response>, Integer, Hash)> get_task_by_id_with_http_info(ext_id, opts)

```ruby
begin
  # Fetch a task
  data, status_code, headers = api_instance.get_task_by_id_with_http_info(ext_id, opts)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <GetTaskById200Response>
rescue NutanixPrism::ApiError => e
  puts "Error when calling TasksApi->get_task_by_id_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **ext_id** | **String** | A globally unique identifier of a task. It consists of a prefix and a UUID separated by &#39;:&#39;. &#39;legacy&#39; prefix can be used with a task UUID provided by previous API families. |  |
| **select** | **String** | A URL query parameter that allows clients to request a specific set of properties for each entity or complex type. Expression specified with the $select must conform to the [OData V4.01](https://docs.oasis-open.org/odata/odata/v4.01/odata-v4.01-part1-protocol.html) URL conventions. If a $select expression consists of a single select item that is an asterisk (i.e., *), then all properties on the matching resource will be returned. - clusterExtIds - completedTime - completionDetails - createdTime - entitiesAffected - errorMessages - extId - isBackgroundTask - isCancelable - lastUpdatedTime - numberOfEntitiesAffected - numberOfSubtasks - operation - operationDescription - ownedBy/extId - ownedBy/name - parentTask - progressPercentage - rootTask - startedTime - status - subTasks - warnings  | [optional] |

### Return type

[**GetTaskById200Response**](GetTaskById200Response.md)

### Authorization

[apiKeyAuthScheme](../README.md#apiKeyAuthScheme), [basicAuthScheme](../README.md#basicAuthScheme)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json


## list_tasks

> <ListTasks200Response> list_tasks(opts)

List tasks

List tasks in the system. The response can be further filtered / sorted using the filtering and sorting options provided. By default the response would be sorted by 'createdTime' in the descending order.

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

api_instance = NutanixPrism::TasksApi.new
opts = {
  page: 56, # Integer | A URL query parameter that specifies the page number of the result set. It must be a positive integer between 0 and the maximum number of pages that are available for that resource. Any number out of this range might lead to no results. 
  limit: 56, # Integer | A URL query parameter that specifies the total number of records returned in the result set.  Must be a positive integer between 1 and 100. Any number out of this range will lead to a validation error. If the limit is not provided, a default value of 50 records will be returned in the result set. 
  filter: 'filter_example', # String | A URL query parameter that allows clients to filter a collection of resources. The expression specified with $filter is evaluated for each resource in the collection, and only items where the expression evaluates to true are included in the response. Expression specified with the $filter must conform to the [OData V4.01](https://docs.oasis-open.org/odata/odata/v4.01/odata-v4.01-part1-protocol.html) URL conventions. For example, filter '$filter=name eq 'karbon-ntnx-1.0' would filter the result on cluster name 'karbon-ntnx1.0', filter '$filter=startswith(name, 'C')' would filter on cluster name starting with 'C'. The filter can be applied to the following fields: - clusterExtIds - completedTime - createdTime - entitiesAffected/extId - entitiesAffected/name - entitiesAffected/rel - extId - isBackgroundTask - lastUpdatedTime - operation - operationDescription - ownedBy/extId - ownedBy/name - parentTask - progressPercentage - rootTask - startedTime - status 
  orderby: 'orderby_example', # String | A URL query parameter that allows clients to specify the sort criteria for the returned list of objects. Resources can be sorted in ascending order using asc or descending order using desc. If asc or desc are not specified, the resources will be sorted in ascending order by default. For example, '$orderby=templateName desc' would get all templates sorted by templateName in descending order. The orderby can be applied to the following fields: - completedTime - createdTime - lastUpdatedTime - operation - operationDescription - ownedBy/extId - ownedBy/name - progressPercentage - startedTime - status 
  select: 'select_example' # String | A URL query parameter that allows clients to request a specific set of properties for each entity or complex type. Expression specified with the $select must conform to the [OData V4.01](https://docs.oasis-open.org/odata/odata/v4.01/odata-v4.01-part1-protocol.html) URL conventions. If a $select expression consists of a single select item that is an asterisk (i.e., *), then all properties on the matching resource will be returned. - clusterExtIds - completedTime - completionDetails - createdTime - entitiesAffected - errorMessages - extId - isBackgroundTask - isCancelable - lastUpdatedTime - numberOfEntitiesAffected - numberOfSubtasks - operation - operationDescription - ownedBy/extId - ownedBy/name - parentTask - progressPercentage - rootTask - startedTime - status - subTasks - warnings 
}

begin
  # List tasks
  result = api_instance.list_tasks(opts)
  p result
rescue NutanixPrism::ApiError => e
  puts "Error when calling TasksApi->list_tasks: #{e}"
end
```

#### Using the list_tasks_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<ListTasks200Response>, Integer, Hash)> list_tasks_with_http_info(opts)

```ruby
begin
  # List tasks
  data, status_code, headers = api_instance.list_tasks_with_http_info(opts)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <ListTasks200Response>
rescue NutanixPrism::ApiError => e
  puts "Error when calling TasksApi->list_tasks_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **page** | **Integer** | A URL query parameter that specifies the page number of the result set. It must be a positive integer between 0 and the maximum number of pages that are available for that resource. Any number out of this range might lead to no results.  | [optional][default to 0] |
| **limit** | **Integer** | A URL query parameter that specifies the total number of records returned in the result set.  Must be a positive integer between 1 and 100. Any number out of this range will lead to a validation error. If the limit is not provided, a default value of 50 records will be returned in the result set.  | [optional][default to 50] |
| **filter** | **String** | A URL query parameter that allows clients to filter a collection of resources. The expression specified with $filter is evaluated for each resource in the collection, and only items where the expression evaluates to true are included in the response. Expression specified with the $filter must conform to the [OData V4.01](https://docs.oasis-open.org/odata/odata/v4.01/odata-v4.01-part1-protocol.html) URL conventions. For example, filter &#39;$filter&#x3D;name eq &#39;karbon-ntnx-1.0&#39; would filter the result on cluster name &#39;karbon-ntnx1.0&#39;, filter &#39;$filter&#x3D;startswith(name, &#39;C&#39;)&#39; would filter on cluster name starting with &#39;C&#39;. The filter can be applied to the following fields: - clusterExtIds - completedTime - createdTime - entitiesAffected/extId - entitiesAffected/name - entitiesAffected/rel - extId - isBackgroundTask - lastUpdatedTime - operation - operationDescription - ownedBy/extId - ownedBy/name - parentTask - progressPercentage - rootTask - startedTime - status  | [optional] |
| **orderby** | **String** | A URL query parameter that allows clients to specify the sort criteria for the returned list of objects. Resources can be sorted in ascending order using asc or descending order using desc. If asc or desc are not specified, the resources will be sorted in ascending order by default. For example, &#39;$orderby&#x3D;templateName desc&#39; would get all templates sorted by templateName in descending order. The orderby can be applied to the following fields: - completedTime - createdTime - lastUpdatedTime - operation - operationDescription - ownedBy/extId - ownedBy/name - progressPercentage - startedTime - status  | [optional] |
| **select** | **String** | A URL query parameter that allows clients to request a specific set of properties for each entity or complex type. Expression specified with the $select must conform to the [OData V4.01](https://docs.oasis-open.org/odata/odata/v4.01/odata-v4.01-part1-protocol.html) URL conventions. If a $select expression consists of a single select item that is an asterisk (i.e., *), then all properties on the matching resource will be returned. - clusterExtIds - completedTime - completionDetails - createdTime - entitiesAffected - errorMessages - extId - isBackgroundTask - isCancelable - lastUpdatedTime - numberOfEntitiesAffected - numberOfSubtasks - operation - operationDescription - ownedBy/extId - ownedBy/name - parentTask - progressPercentage - rootTask - startedTime - status - subTasks - warnings  | [optional] |

### Return type

[**ListTasks200Response**](ListTasks200Response.md)

### Authorization

[apiKeyAuthScheme](../README.md#apiKeyAuthScheme), [basicAuthScheme](../README.md#basicAuthScheme)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json

