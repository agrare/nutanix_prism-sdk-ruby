# NutanixPrism::ListRestorePoints200Response

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **metadata** | [**CommonV10ResponseApiResponseMetadata**](CommonV10ResponseApiResponseMetadata.md) |  | [optional] |
| **data** | [**Array&lt;PrismV40ManagementRestorePoint&gt;**](PrismV40ManagementRestorePoint.md) |  | [optional] |

## Example

```ruby
require 'nutanix_prism'

instance = NutanixPrism::ListRestorePoints200Response.new(
  metadata: null,
  data: null
)
```

