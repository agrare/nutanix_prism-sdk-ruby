# NutanixPrism::PrismV40ManagementGetBackupTargetApiResponseData

## Class instance methods

### `openapi_one_of`

Returns the list of classes defined in oneOf.

#### Example

```ruby
require 'nutanix_prism'

NutanixPrism::PrismV40ManagementGetBackupTargetApiResponseData.openapi_one_of
# =>
# [
#   :'PrismV40ErrorErrorResponse',
#   :'PrismV40ManagementBackupTarget'
# ]
```

### build

Find the appropriate object from the `openapi_one_of` list and casts the data into it.

#### Example

```ruby
require 'nutanix_prism'

NutanixPrism::PrismV40ManagementGetBackupTargetApiResponseData.build(data)
# => #<PrismV40ErrorErrorResponse:0x00007fdd4aab02a0>

NutanixPrism::PrismV40ManagementGetBackupTargetApiResponseData.build(data_that_doesnt_match)
# => nil
```

#### Parameters

| Name | Type | Description |
| ---- | ---- | ----------- |
| **data** | **Mixed** | data to be matched against the list of oneOf items |

#### Return type

- `PrismV40ErrorErrorResponse`
- `PrismV40ManagementBackupTarget`
- `nil` (if no type matches)

