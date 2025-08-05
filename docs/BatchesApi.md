# NutanixPrism::BatchesApi

All URIs are relative to *https://:9440/api*

| Method | HTTP request | Description |
| ------ | ------------ | ----------- |
| [**get_batch_by_id**](BatchesApi.md#get_batch_by_id) | **GET** /prism/v4.0/operations/batches/{extId} | Get a Batch identified by {extId}. |
| [**list_batches**](BatchesApi.md#list_batches) | **GET** /prism/v4.0/operations/batches | Get a list of all the Batches. |
| [**submit_batch**](BatchesApi.md#submit_batch) | **POST** /prism/v4.0/operations/$actions/batch | Submit a batch operation. |


## get_batch_by_id

> <GetBatchById200Response> get_batch_by_id(ext_id)

Get a Batch identified by {extId}.

Query the Batch identified by {extId}.

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

api_instance = NutanixPrism::BatchesApi.new
ext_id = '859e3096-6f94-422e-8623-2b203322cad6' # String | The external identifier of the Batch.

begin
  # Get a Batch identified by {extId}.
  result = api_instance.get_batch_by_id(ext_id)
  p result
rescue NutanixPrism::ApiError => e
  puts "Error when calling BatchesApi->get_batch_by_id: #{e}"
end
```

#### Using the get_batch_by_id_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<GetBatchById200Response>, Integer, Hash)> get_batch_by_id_with_http_info(ext_id)

```ruby
begin
  # Get a Batch identified by {extId}.
  data, status_code, headers = api_instance.get_batch_by_id_with_http_info(ext_id)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <GetBatchById200Response>
rescue NutanixPrism::ApiError => e
  puts "Error when calling BatchesApi->get_batch_by_id_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **ext_id** | **String** | The external identifier of the Batch. |  |

### Return type

[**GetBatchById200Response**](GetBatchById200Response.md)

### Authorization

[apiKeyAuthScheme](../README.md#apiKeyAuthScheme), [basicAuthScheme](../README.md#basicAuthScheme)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json


## list_batches

> <ListBatches200Response> list_batches(opts)

Get a list of all the Batches.

Query the list of Batches.

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

api_instance = NutanixPrism::BatchesApi.new
opts = {
  page: 56, # Integer | A URL query parameter that specifies the page number of the result set. It must be a positive integer between 0 and the maximum number of pages that are available for that resource. Any number out of this range might lead to no results. 
  limit: 56, # Integer | A URL query parameter that specifies the total number of records returned in the result set.  Must be a positive integer between 1 and 100. Any number out of this range will lead to a validation error. If the limit is not provided, a default value of 50 records will be returned in the result set. 
  filter: 'filter_example', # String | A URL query parameter that allows clients to filter a collection of resources. The expression specified with $filter is evaluated for each resource in the collection, and only items where the expression evaluates to true are included in the response. Expression specified with the $filter must conform to the [OData V4.01](https://docs.oasis-open.org/odata/odata/v4.01/odata-v4.01-part1-protocol.html) URL conventions. For example, filter '$filter=name eq 'karbon-ntnx-1.0' would filter the result on cluster name 'karbon-ntnx1.0', filter '$filter=startswith(name, 'C')' would filter on cluster name starting with 'C'. The filter can be applied to the following fields: - name 
  orderby: 'orderby_example', # String | A URL query parameter that allows clients to specify the sort criteria for the returned list of objects. Resources can be sorted in ascending order using asc or descending order using desc. If asc or desc are not specified, the resources will be sorted in ascending order by default. For example, '$orderby=templateName desc' would get all templates sorted by templateName in descending order. The orderby can be applied to the following fields: - endTime - name - startTime 
  select: 'select_example' # String | A URL query parameter that allows clients to request a specific set of properties for each entity or complex type. Expression specified with the $select must conform to the [OData V4.01](https://docs.oasis-open.org/odata/odata/v4.01/odata-v4.01-part1-protocol.html) URL conventions. If a $select expression consists of a single select item that is an asterisk (i.e., *), then all properties on the matching resource will be returned. - completionStatus - endTime - executionStatus - extId - failedCount - links - name - shouldStopOnError - size - startTime - successCount - tenantId 
}

begin
  # Get a list of all the Batches.
  result = api_instance.list_batches(opts)
  p result
rescue NutanixPrism::ApiError => e
  puts "Error when calling BatchesApi->list_batches: #{e}"
end
```

#### Using the list_batches_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<ListBatches200Response>, Integer, Hash)> list_batches_with_http_info(opts)

```ruby
begin
  # Get a list of all the Batches.
  data, status_code, headers = api_instance.list_batches_with_http_info(opts)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <ListBatches200Response>
rescue NutanixPrism::ApiError => e
  puts "Error when calling BatchesApi->list_batches_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **page** | **Integer** | A URL query parameter that specifies the page number of the result set. It must be a positive integer between 0 and the maximum number of pages that are available for that resource. Any number out of this range might lead to no results.  | [optional][default to 0] |
| **limit** | **Integer** | A URL query parameter that specifies the total number of records returned in the result set.  Must be a positive integer between 1 and 100. Any number out of this range will lead to a validation error. If the limit is not provided, a default value of 50 records will be returned in the result set.  | [optional][default to 50] |
| **filter** | **String** | A URL query parameter that allows clients to filter a collection of resources. The expression specified with $filter is evaluated for each resource in the collection, and only items where the expression evaluates to true are included in the response. Expression specified with the $filter must conform to the [OData V4.01](https://docs.oasis-open.org/odata/odata/v4.01/odata-v4.01-part1-protocol.html) URL conventions. For example, filter &#39;$filter&#x3D;name eq &#39;karbon-ntnx-1.0&#39; would filter the result on cluster name &#39;karbon-ntnx1.0&#39;, filter &#39;$filter&#x3D;startswith(name, &#39;C&#39;)&#39; would filter on cluster name starting with &#39;C&#39;. The filter can be applied to the following fields: - name  | [optional] |
| **orderby** | **String** | A URL query parameter that allows clients to specify the sort criteria for the returned list of objects. Resources can be sorted in ascending order using asc or descending order using desc. If asc or desc are not specified, the resources will be sorted in ascending order by default. For example, &#39;$orderby&#x3D;templateName desc&#39; would get all templates sorted by templateName in descending order. The orderby can be applied to the following fields: - endTime - name - startTime  | [optional] |
| **select** | **String** | A URL query parameter that allows clients to request a specific set of properties for each entity or complex type. Expression specified with the $select must conform to the [OData V4.01](https://docs.oasis-open.org/odata/odata/v4.01/odata-v4.01-part1-protocol.html) URL conventions. If a $select expression consists of a single select item that is an asterisk (i.e., *), then all properties on the matching resource will be returned. - completionStatus - endTime - executionStatus - extId - failedCount - links - name - shouldStopOnError - size - startTime - successCount - tenantId  | [optional] |

### Return type

[**ListBatches200Response**](ListBatches200Response.md)

### Authorization

[apiKeyAuthScheme](../README.md#apiKeyAuthScheme), [basicAuthScheme](../README.md#basicAuthScheme)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json


## submit_batch

> <SubmitBatch202Response> submit_batch(ntnx_request_id, prism_v40_operations_batch_spec)

Submit a batch operation.

Submit a homogenous batch operation.

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

api_instance = NutanixPrism::BatchesApi.new
ntnx_request_id = 'f895be15-854e-4072-a016-84ad00256994' # String | A unique identifier that is associated with each request. The provided value must be opaque and preferably in Universal Unique Identifier (UUID) format. This identifier is also used as an idempotence token for safely retrying requests in case of network errors. All the supported Nutanix API clients add this auto-generated request identifier to each request. 
prism_v40_operations_batch_spec = NutanixPrism::PrismV40OperationsBatchSpec.new # PrismV40OperationsBatchSpec | The request payload for the batch operation.

begin
  # Submit a batch operation.
  result = api_instance.submit_batch(ntnx_request_id, prism_v40_operations_batch_spec)
  p result
rescue NutanixPrism::ApiError => e
  puts "Error when calling BatchesApi->submit_batch: #{e}"
end
```

#### Using the submit_batch_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<SubmitBatch202Response>, Integer, Hash)> submit_batch_with_http_info(ntnx_request_id, prism_v40_operations_batch_spec)

```ruby
begin
  # Submit a batch operation.
  data, status_code, headers = api_instance.submit_batch_with_http_info(ntnx_request_id, prism_v40_operations_batch_spec)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <SubmitBatch202Response>
rescue NutanixPrism::ApiError => e
  puts "Error when calling BatchesApi->submit_batch_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **ntnx_request_id** | **String** | A unique identifier that is associated with each request. The provided value must be opaque and preferably in Universal Unique Identifier (UUID) format. This identifier is also used as an idempotence token for safely retrying requests in case of network errors. All the supported Nutanix API clients add this auto-generated request identifier to each request.  |  |
| **prism_v40_operations_batch_spec** | [**PrismV40OperationsBatchSpec**](PrismV40OperationsBatchSpec.md) | The request payload for the batch operation. |  |

### Return type

[**SubmitBatch202Response**](SubmitBatch202Response.md)

### Authorization

[apiKeyAuthScheme](../README.md#apiKeyAuthScheme), [basicAuthScheme](../README.md#basicAuthScheme)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json

