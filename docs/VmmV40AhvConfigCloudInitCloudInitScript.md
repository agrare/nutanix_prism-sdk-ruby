# NutanixPrism::VmmV40AhvConfigCloudInitCloudInitScript

## Class instance methods

### `openapi_one_of`

Returns the list of classes defined in oneOf.

#### Example

```ruby
require 'nutanix_prism'

NutanixPrism::VmmV40AhvConfigCloudInitCloudInitScript.openapi_one_of
# =>
# [
#   :'VmmV40AhvConfigCustomKeyValues',
#   :'VmmV40AhvConfigUserdata'
# ]
```

### build

Find the appropriate object from the `openapi_one_of` list and casts the data into it.

#### Example

```ruby
require 'nutanix_prism'

NutanixPrism::VmmV40AhvConfigCloudInitCloudInitScript.build(data)
# => #<VmmV40AhvConfigCustomKeyValues:0x00007fdd4aab02a0>

NutanixPrism::VmmV40AhvConfigCloudInitCloudInitScript.build(data_that_doesnt_match)
# => nil
```

#### Parameters

| Name | Type | Description |
| ---- | ---- | ----------- |
| **data** | **Mixed** | data to be matched against the list of oneOf items |

#### Return type

- `VmmV40AhvConfigCustomKeyValues`
- `VmmV40AhvConfigUserdata`
- `nil` (if no type matches)

