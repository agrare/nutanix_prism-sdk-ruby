# NutanixPrism::ListRestorableDomainManagers200Response

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **metadata** | [**CommonV10ResponseApiResponseMetadata**](CommonV10ResponseApiResponseMetadata.md) |  | [optional] |
| **data** | [**Array&lt;PrismV40ManagementRestorableDomainManager&gt;**](PrismV40ManagementRestorableDomainManager.md) |  | [optional] |

## Example

```ruby
require 'nutanix_prism'

instance = NutanixPrism::ListRestorableDomainManagers200Response.new(
  metadata: null,
  data: null
)
```

