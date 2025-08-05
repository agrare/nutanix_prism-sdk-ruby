# NutanixPrism::PrismV40OperationsListBatchesApiResponseData

## Class instance methods

### `openapi_one_of`

Returns the list of classes defined in oneOf.

#### Example

```ruby
require 'nutanix_prism'

NutanixPrism::PrismV40OperationsListBatchesApiResponseData.openapi_one_of
# =>
# [
#   :'Array<PrismV40OperationsBatch>',
#   :'PrismV40ErrorErrorResponse'
# ]
```

### build

Find the appropriate object from the `openapi_one_of` list and casts the data into it.

#### Example

```ruby
require 'nutanix_prism'

NutanixPrism::PrismV40OperationsListBatchesApiResponseData.build(data)
# => #<Array<PrismV40OperationsBatch>:0x00007fdd4aab02a0>

NutanixPrism::PrismV40OperationsListBatchesApiResponseData.build(data_that_doesnt_match)
# => nil
```

#### Parameters

| Name | Type | Description |
| ---- | ---- | ----------- |
| **data** | **Mixed** | data to be matched against the list of oneOf items |

#### Return type

- `Array<PrismV40OperationsBatch>`
- `PrismV40ErrorErrorResponse`
- `nil` (if no type matches)

