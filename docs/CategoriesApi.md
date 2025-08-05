# NutanixPrism::CategoriesApi

All URIs are relative to *https://:9440/api*

| Method | HTTP request | Description |
| ------ | ------------ | ----------- |
| [**create_category**](CategoriesApi.md#create_category) | **POST** /prism/v4.0/config/categories | Create a category  |
| [**delete_category_by_id**](CategoriesApi.md#delete_category_by_id) | **DELETE** /prism/v4.0/config/categories/{extId} | Delete a category  |
| [**get_category_by_id**](CategoriesApi.md#get_category_by_id) | **GET** /prism/v4.0/config/categories/{extId} | Fetch a category  |
| [**list_categories**](CategoriesApi.md#list_categories) | **GET** /prism/v4.0/config/categories | List categories  |
| [**update_category_by_id**](CategoriesApi.md#update_category_by_id) | **PUT** /prism/v4.0/config/categories/{extId} | Update a category  |


## create_category

> <CreateCategory201Response> create_category(prism_v40_config_category)

Create a category 

Creates a category with a given key and value pair. 

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

api_instance = NutanixPrism::CategoriesApi.new
prism_v40_config_category = NutanixPrism::PrismV40ConfigCategory.new({key: 'AvailabilityZone', value: 'APAC'}) # PrismV40ConfigCategory | 

begin
  # Create a category 
  result = api_instance.create_category(prism_v40_config_category)
  p result
rescue NutanixPrism::ApiError => e
  puts "Error when calling CategoriesApi->create_category: #{e}"
end
```

#### Using the create_category_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<CreateCategory201Response>, Integer, Hash)> create_category_with_http_info(prism_v40_config_category)

```ruby
begin
  # Create a category 
  data, status_code, headers = api_instance.create_category_with_http_info(prism_v40_config_category)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <CreateCategory201Response>
rescue NutanixPrism::ApiError => e
  puts "Error when calling CategoriesApi->create_category_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **prism_v40_config_category** | [**PrismV40ConfigCategory**](PrismV40ConfigCategory.md) |  |  |

### Return type

[**CreateCategory201Response**](CreateCategory201Response.md)

### Authorization

[apiKeyAuthScheme](../README.md#apiKeyAuthScheme), [basicAuthScheme](../README.md#basicAuthScheme)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json


## delete_category_by_id

> delete_category_by_id(ext_id)

Delete a category 

Deletes a category with the given external identifier. 

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

api_instance = NutanixPrism::CategoriesApi.new
ext_id = 'e8feb788-d169-446c-beb9-0d104a433d4a' # String | A globally unique identifier of an instance that is suitable for external consumption. 

begin
  # Delete a category 
  api_instance.delete_category_by_id(ext_id)
rescue NutanixPrism::ApiError => e
  puts "Error when calling CategoriesApi->delete_category_by_id: #{e}"
end
```

#### Using the delete_category_by_id_with_http_info variant

This returns an Array which contains the response data (`nil` in this case), status code and headers.

> <Array(nil, Integer, Hash)> delete_category_by_id_with_http_info(ext_id)

```ruby
begin
  # Delete a category 
  data, status_code, headers = api_instance.delete_category_by_id_with_http_info(ext_id)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => nil
rescue NutanixPrism::ApiError => e
  puts "Error when calling CategoriesApi->delete_category_by_id_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **ext_id** | **String** | A globally unique identifier of an instance that is suitable for external consumption.  |  |

### Return type

nil (empty response body)

### Authorization

[apiKeyAuthScheme](../README.md#apiKeyAuthScheme), [basicAuthScheme](../README.md#basicAuthScheme)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json


## get_category_by_id

> <GetCategoryById200Response> get_category_by_id(ext_id, opts)

Fetch a category 

Fetches the details of a category with the given external identifier. 

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

api_instance = NutanixPrism::CategoriesApi.new
ext_id = '85e68112-5b2b-4220-bc8d-e529e4bf420e' # String | A globally unique identifier of an instance that is suitable for external consumption. 
opts = {
  expand: 'expand_example' # String | A URL query parameter that allows clients to request related resources when a resource that satisfies a particular request is retrieved. Each expanded item is evaluated relative to the entity containing the property being expanded. Other query options can be applied to an expanded property by appending a semicolon-separated list of query options, enclosed in parentheses, to the property name. Permissible system query options are $filter, $select and $orderby. The following expansion keys are supported. - associations - detailedAssociations 
}

begin
  # Fetch a category 
  result = api_instance.get_category_by_id(ext_id, opts)
  p result
rescue NutanixPrism::ApiError => e
  puts "Error when calling CategoriesApi->get_category_by_id: #{e}"
end
```

#### Using the get_category_by_id_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<GetCategoryById200Response>, Integer, Hash)> get_category_by_id_with_http_info(ext_id, opts)

```ruby
begin
  # Fetch a category 
  data, status_code, headers = api_instance.get_category_by_id_with_http_info(ext_id, opts)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <GetCategoryById200Response>
rescue NutanixPrism::ApiError => e
  puts "Error when calling CategoriesApi->get_category_by_id_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **ext_id** | **String** | A globally unique identifier of an instance that is suitable for external consumption.  |  |
| **expand** | **String** | A URL query parameter that allows clients to request related resources when a resource that satisfies a particular request is retrieved. Each expanded item is evaluated relative to the entity containing the property being expanded. Other query options can be applied to an expanded property by appending a semicolon-separated list of query options, enclosed in parentheses, to the property name. Permissible system query options are $filter, $select and $orderby. The following expansion keys are supported. - associations - detailedAssociations  | [optional] |

### Return type

[**GetCategoryById200Response**](GetCategoryById200Response.md)

### Authorization

[apiKeyAuthScheme](../README.md#apiKeyAuthScheme), [basicAuthScheme](../README.md#basicAuthScheme)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json


## list_categories

> <ListCategories200Response> list_categories(opts)

List categories 

Fetches a list of categories with pagination, filtering, sorting, selection, and optional expansion of associated entity counts. 

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

api_instance = NutanixPrism::CategoriesApi.new
opts = {
  page: 56, # Integer | A URL query parameter that specifies the page number of the result set. It must be a positive integer between 0 and the maximum number of pages that are available for that resource. Any number out of this range might lead to no results. 
  limit: 56, # Integer | A URL query parameter that specifies the total number of records returned in the result set.  Must be a positive integer between 1 and 100. Any number out of this range will lead to a validation error. If the limit is not provided, a default value of 50 records will be returned in the result set. 
  filter: 'filter_example', # String | A URL query parameter that allows clients to filter a collection of resources. The expression specified with $filter is evaluated for each resource in the collection, and only items where the expression evaluates to true are included in the response. Expression specified with the $filter must conform to the [OData V4.01](https://docs.oasis-open.org/odata/odata/v4.01/odata-v4.01-part1-protocol.html) URL conventions. For example, filter '$filter=name eq 'karbon-ntnx-1.0' would filter the result on cluster name 'karbon-ntnx1.0', filter '$filter=startswith(name, 'C')' would filter on cluster name starting with 'C'. The filter can be applied to the following fields: - extId - key - ownerUuid - type - value 
  orderby: 'orderby_example', # String | A URL query parameter that allows clients to specify the sort criteria for the returned list of objects. Resources can be sorted in ascending order using asc or descending order using desc. If asc or desc are not specified, the resources will be sorted in ascending order by default. For example, '$orderby=templateName desc' would get all templates sorted by templateName in descending order. The orderby can be applied to the following fields: - key - value 
  expand: 'expand_example', # String | A URL query parameter that allows clients to request related resources when a resource that satisfies a particular request is retrieved. Each expanded item is evaluated relative to the entity containing the property being expanded. Other query options can be applied to an expanded property by appending a semicolon-separated list of query options, enclosed in parentheses, to the property name. Permissible system query options are $filter, $select and $orderby. The following expansion keys are supported. - associations - detailedAssociations 
  select: 'select_example' # String | A URL query parameter that allows clients to request a specific set of properties for each entity or complex type. Expression specified with the $select must conform to the [OData V4.01](https://docs.oasis-open.org/odata/odata/v4.01/odata-v4.01-part1-protocol.html) URL conventions. If a $select expression consists of a single select item that is an asterisk (i.e., *), then all properties on the matching resource will be returned. - description - extId - key - ownerUuid - type - value 
}

begin
  # List categories 
  result = api_instance.list_categories(opts)
  p result
rescue NutanixPrism::ApiError => e
  puts "Error when calling CategoriesApi->list_categories: #{e}"
end
```

#### Using the list_categories_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<ListCategories200Response>, Integer, Hash)> list_categories_with_http_info(opts)

```ruby
begin
  # List categories 
  data, status_code, headers = api_instance.list_categories_with_http_info(opts)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <ListCategories200Response>
rescue NutanixPrism::ApiError => e
  puts "Error when calling CategoriesApi->list_categories_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **page** | **Integer** | A URL query parameter that specifies the page number of the result set. It must be a positive integer between 0 and the maximum number of pages that are available for that resource. Any number out of this range might lead to no results.  | [optional][default to 0] |
| **limit** | **Integer** | A URL query parameter that specifies the total number of records returned in the result set.  Must be a positive integer between 1 and 100. Any number out of this range will lead to a validation error. If the limit is not provided, a default value of 50 records will be returned in the result set.  | [optional][default to 50] |
| **filter** | **String** | A URL query parameter that allows clients to filter a collection of resources. The expression specified with $filter is evaluated for each resource in the collection, and only items where the expression evaluates to true are included in the response. Expression specified with the $filter must conform to the [OData V4.01](https://docs.oasis-open.org/odata/odata/v4.01/odata-v4.01-part1-protocol.html) URL conventions. For example, filter &#39;$filter&#x3D;name eq &#39;karbon-ntnx-1.0&#39; would filter the result on cluster name &#39;karbon-ntnx1.0&#39;, filter &#39;$filter&#x3D;startswith(name, &#39;C&#39;)&#39; would filter on cluster name starting with &#39;C&#39;. The filter can be applied to the following fields: - extId - key - ownerUuid - type - value  | [optional] |
| **orderby** | **String** | A URL query parameter that allows clients to specify the sort criteria for the returned list of objects. Resources can be sorted in ascending order using asc or descending order using desc. If asc or desc are not specified, the resources will be sorted in ascending order by default. For example, &#39;$orderby&#x3D;templateName desc&#39; would get all templates sorted by templateName in descending order. The orderby can be applied to the following fields: - key - value  | [optional] |
| **expand** | **String** | A URL query parameter that allows clients to request related resources when a resource that satisfies a particular request is retrieved. Each expanded item is evaluated relative to the entity containing the property being expanded. Other query options can be applied to an expanded property by appending a semicolon-separated list of query options, enclosed in parentheses, to the property name. Permissible system query options are $filter, $select and $orderby. The following expansion keys are supported. - associations - detailedAssociations  | [optional] |
| **select** | **String** | A URL query parameter that allows clients to request a specific set of properties for each entity or complex type. Expression specified with the $select must conform to the [OData V4.01](https://docs.oasis-open.org/odata/odata/v4.01/odata-v4.01-part1-protocol.html) URL conventions. If a $select expression consists of a single select item that is an asterisk (i.e., *), then all properties on the matching resource will be returned. - description - extId - key - ownerUuid - type - value  | [optional] |

### Return type

[**ListCategories200Response**](ListCategories200Response.md)

### Authorization

[apiKeyAuthScheme](../README.md#apiKeyAuthScheme), [basicAuthScheme](../README.md#basicAuthScheme)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json


## update_category_by_id

> <UpdateCategoryById200Response> update_category_by_id(ext_id, if_match, prism_v40_config_category)

Update a category 

Updates the description, value, and owner properties of a category. 

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

api_instance = NutanixPrism::CategoriesApi.new
ext_id = 'e0af1b08-84ff-404e-829e-fff7350e805e' # String | A globally unique identifier of an instance that is suitable for external consumption. 
if_match = 'if_match_example' # String | The If-Match request header makes the request conditional. When not provided, the server will respond with  an HTTP-428 (Precondition Required) response code indicating that the server requires the request to be conditional. The server will allow the successful completion of PUT and PATCH operations, if the resource matches the ETag value returned to the response of a GET operation. If the conditional does not match, then an HTTP-412 (Precondition Failed) response will be returned.
prism_v40_config_category = NutanixPrism::PrismV40ConfigCategory.new({key: 'AvailabilityZone', value: 'APAC'}) # PrismV40ConfigCategory | 

begin
  # Update a category 
  result = api_instance.update_category_by_id(ext_id, if_match, prism_v40_config_category)
  p result
rescue NutanixPrism::ApiError => e
  puts "Error when calling CategoriesApi->update_category_by_id: #{e}"
end
```

#### Using the update_category_by_id_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(<UpdateCategoryById200Response>, Integer, Hash)> update_category_by_id_with_http_info(ext_id, if_match, prism_v40_config_category)

```ruby
begin
  # Update a category 
  data, status_code, headers = api_instance.update_category_by_id_with_http_info(ext_id, if_match, prism_v40_config_category)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => <UpdateCategoryById200Response>
rescue NutanixPrism::ApiError => e
  puts "Error when calling CategoriesApi->update_category_by_id_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **ext_id** | **String** | A globally unique identifier of an instance that is suitable for external consumption.  |  |
| **if_match** | **String** | The If-Match request header makes the request conditional. When not provided, the server will respond with  an HTTP-428 (Precondition Required) response code indicating that the server requires the request to be conditional. The server will allow the successful completion of PUT and PATCH operations, if the resource matches the ETag value returned to the response of a GET operation. If the conditional does not match, then an HTTP-412 (Precondition Failed) response will be returned. |  |
| **prism_v40_config_category** | [**PrismV40ConfigCategory**](PrismV40ConfigCategory.md) |  |  |

### Return type

[**UpdateCategoryById200Response**](UpdateCategoryById200Response.md)

### Authorization

[apiKeyAuthScheme](../README.md#apiKeyAuthScheme), [basicAuthScheme](../README.md#basicAuthScheme)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json

