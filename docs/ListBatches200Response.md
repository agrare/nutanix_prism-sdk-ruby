# NutanixPrism::ListBatches200Response

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **metadata** | [**CommonV10ResponseApiResponseMetadata**](CommonV10ResponseApiResponseMetadata.md) |  | [optional] |
| **data** | [**Array&lt;PrismV40OperationsBatch&gt;**](PrismV40OperationsBatch.md) |  | [optional] |

## Example

```ruby
require 'nutanix_prism'

instance = NutanixPrism::ListBatches200Response.new(
  metadata: null,
  data: null
)
```

