# NutanixPrism::PrismV40OperationsBatchSpecPayload

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **metadata** | [**PrismV40OperationsBatchSpecPayloadMetadata**](PrismV40OperationsBatchSpecPayloadMetadata.md) |  | [optional] |
| **data** | **Hash&lt;String, Object&gt;** | The data section of the payload provided to the batch operation. | [optional] |

## Example

```ruby
require 'nutanix_prism'

instance = NutanixPrism::PrismV40OperationsBatchSpecPayload.new(
  metadata: null,
  data: null
)
```

