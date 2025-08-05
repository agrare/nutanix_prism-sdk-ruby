# NutanixPrism::PrismV40ConfigDomainManager

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **tenant_id** | **String** | A globally unique identifier that represents the tenant that owns this entity. The system automatically assigns it, and it and is immutable from an API consumer perspective (some use cases may cause this Id to change - For instance, a use case may require the transfer of ownership of the entity, but these cases are handled automatically on the server).  | [optional][readonly] |
| **ext_id** | **String** | A globally unique identifier of an instance that is suitable for external consumption.  | [optional][readonly] |
| **links** | [**Array&lt;CommonV10ResponseApiLink&gt;**](CommonV10ResponseApiLink.md) | A HATEOAS style link for the response.  Each link contains a user-friendly name identifying the link and an address for retrieving the particular resource.  | [optional][readonly] |
| **config** | [**PrismV40ConfigDomainManagerClusterConfig**](PrismV40ConfigDomainManagerClusterConfig.md) |  |  |
| **is_registered_with_hosting_cluster** | **Boolean** | Boolean value indicating if the domain manager (Prism Central) is registered with the hosting cluster, that is, Prism Element. | [optional][readonly] |
| **network** | [**PrismV40ConfigDomainManagerNetwork**](PrismV40ConfigDomainManagerNetwork.md) |  |  |
| **hosting_cluster_ext_id** | **String** | The external identifier of the cluster hosting the domain manager (Prism Central) instance. | [optional][readonly] |
| **should_enable_high_availability** | **Boolean** | This configuration enables Prism Central to be deployed in scale-out mode. | [optional][default to false] |
| **node_ext_ids** | **Array&lt;String&gt;** | Domain manager (Prism Central) nodes external identifier. | [optional][readonly] |

## Example

```ruby
require 'nutanix_prism'

instance = NutanixPrism::PrismV40ConfigDomainManager.new(
  tenant_id: d568ff06-a6dc-480f-868c-b85b52f447ba,
  ext_id: 0562e12d-543d-4030-9271-20ba8e72fcb2,
  links: null,
  config: null,
  is_registered_with_hosting_cluster: false,
  network: null,
  hosting_cluster_ext_id: 5d1d9521-780c-4d6d-8a24-75e8fdd94de1,
  should_enable_high_availability: null,
  node_ext_ids: null
)
```

