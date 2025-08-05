# NutanixPrism::PrismV40OperationsBatchSpecMetadata

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **action** | [**PrismV40OperationsActionType**](PrismV40OperationsActionType.md) |  |  |
| **name** | **String** | An user friendly name of the batch. |  |
| **uri** | **String** | The absolute URI of the API operation on which batching will be performed. |  |
| **should_stop_on_error** | **Boolean** | A flag indicating whether the batch procession should halt or continue when an error response is received from the server during the execution of a batch chunk | [optional][default to false] |
| **chunk_size** | **Integer** | The chunk size to use during the batching operation. If not specified a minimum value of 1 would be chosen. | [optional][default to 1] |

## Example

```ruby
require 'nutanix_prism'

instance = NutanixPrism::PrismV40OperationsBatchSpecMetadata.new(
  action: null,
  name: Batch VM Creation,
  uri: /api/vmm/v4.0/ahv/config/vms,
  should_stop_on_error: null,
  chunk_size: null
)
```

