# NutanixPrism::ListDomainManagers200Response

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **metadata** | [**CommonV10ResponseApiResponseMetadata**](CommonV10ResponseApiResponseMetadata.md) |  | [optional] |
| **data** | [**Array&lt;PrismV40ConfigDomainManager&gt;**](PrismV40ConfigDomainManager.md) |  | [optional] |

## Example

```ruby
require 'nutanix_prism'

instance = NutanixPrism::ListDomainManagers200Response.new(
  metadata: null,
  data: null
)
```

