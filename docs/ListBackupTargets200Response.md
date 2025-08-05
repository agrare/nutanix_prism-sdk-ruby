# NutanixPrism::ListBackupTargets200Response

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **metadata** | [**CommonV10ResponseApiResponseMetadata**](CommonV10ResponseApiResponseMetadata.md) |  | [optional] |
| **data** | [**Array&lt;PrismV40ManagementBackupTarget&gt;**](PrismV40ManagementBackupTarget.md) |  | [optional] |

## Example

```ruby
require 'nutanix_prism'

instance = NutanixPrism::ListBackupTargets200Response.new(
  metadata: null,
  data: null
)
```

