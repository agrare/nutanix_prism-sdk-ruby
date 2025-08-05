# NutanixPrism::PrismV40ManagementRestorePoint

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **tenant_id** | **String** | A globally unique identifier that represents the tenant that owns this entity. The system automatically assigns it, and it and is immutable from an API consumer perspective (some use cases may cause this Id to change - For instance, a use case may require the transfer of ownership of the entity, but these cases are handled automatically on the server).  | [optional][readonly] |
| **ext_id** | **String** | A globally unique identifier of an instance that is suitable for external consumption.  | [optional][readonly] |
| **links** | [**Array&lt;CommonV10ResponseApiLink&gt;**](CommonV10ResponseApiLink.md) | A HATEOAS style link for the response.  Each link contains a user-friendly name identifying the link and an address for retrieving the particular resource.  | [optional][readonly] |
| **creation_time** | **Time** | The UTC date and time in ISO-8601 format when the Restore point was created.  | [optional][readonly] |
| **domain_manager** | [**PrismV40ConfigDomainManager**](PrismV40ConfigDomainManager.md) |  | [optional] |

## Example

```ruby
require 'nutanix_prism'

instance = NutanixPrism::PrismV40ManagementRestorePoint.new(
  tenant_id: d568ff06-a6dc-480f-868c-b85b52f447ba,
  ext_id: 0562e12d-543d-4030-9271-20ba8e72fcb2,
  links: null,
  creation_time: 2009-09-23T14:30-07:00,
  domain_manager: null
)
```

