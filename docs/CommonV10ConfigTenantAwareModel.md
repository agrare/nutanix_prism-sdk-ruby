# NutanixPrism::CommonV10ConfigTenantAwareModel

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **tenant_id** | **String** | A globally unique identifier that represents the tenant that owns this entity. The system automatically assigns it, and it and is immutable from an API consumer perspective (some use cases may cause this Id to change - For instance, a use case may require the transfer of ownership of the entity, but these cases are handled automatically on the server).  | [optional][readonly] |

## Example

```ruby
require 'nutanix_prism'

instance = NutanixPrism::CommonV10ConfigTenantAwareModel.new(
  tenant_id: d568ff06-a6dc-480f-868c-b85b52f447ba
)
```

