# NutanixPrism::PrismV40ConfigAssociationDetail

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **tenant_id** | **String** | A globally unique identifier that represents the tenant that owns this entity. The system automatically assigns it, and it and is immutable from an API consumer perspective (some use cases may cause this Id to change - For instance, a use case may require the transfer of ownership of the entity, but these cases are handled automatically on the server).  | [optional][readonly] |
| **ext_id** | **String** | A globally unique identifier of an instance that is suitable for external consumption.  | [optional][readonly] |
| **links** | [**Array&lt;CommonV10ResponseApiLink&gt;**](CommonV10ResponseApiLink.md) | A HATEOAS style link for the response.  Each link contains a user-friendly name identifying the link and an address for retrieving the particular resource.  | [optional][readonly] |
| **category_id** | **String** | External identifier for the given category that is used across all v4 apis/entities/resources where categories are referenced.&lt;br&gt; The field is in UUID format.&lt;br&gt; A type 4 UUID is generated during category creation.  | [optional] |
| **resource_type** | [**PrismV40ConfigResourceType**](PrismV40ConfigResourceType.md) |  | [optional] |
| **resource_group** | [**PrismV40ConfigResourceGroup**](PrismV40ConfigResourceGroup.md) |  | [optional] |
| **resource_id** | **String** | The UUID of the entity or policy associated with the particular category.  | [optional] |

## Example

```ruby
require 'nutanix_prism'

instance = NutanixPrism::PrismV40ConfigAssociationDetail.new(
  tenant_id: d568ff06-a6dc-480f-868c-b85b52f447ba,
  ext_id: 0562e12d-543d-4030-9271-20ba8e72fcb2,
  links: null,
  category_id: 0a817535-bca1-4e50-9395-f1970ebaa2db,
  resource_type: null,
  resource_group: null,
  resource_id: b8f5e88d-32e2-44c6-aa37-a37ffdb557ef
)
```

