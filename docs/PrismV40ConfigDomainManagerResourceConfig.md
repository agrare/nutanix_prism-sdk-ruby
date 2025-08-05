# NutanixPrism::PrismV40ConfigDomainManagerResourceConfig

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **num_vcpus** | **Integer** | This property is used for readOnly purposes to display Prism Central number of VCPUs allocation. | [optional][readonly] |
| **memory_size_bytes** | **Integer** | This property is used for readOnly purposes to display Prism Central RAM allocation at the cluster level. | [optional][readonly] |
| **data_disk_size_bytes** | **Integer** | This property is used for readOnly purposes to display Prism Central data disk size allocation at a cluster level. | [optional][readonly] |
| **container_ext_ids** | **Array&lt;String&gt;** | The external identifier of the container that will be used to create the domain manager (Prism Central) cluster. | [optional] |

## Example

```ruby
require 'nutanix_prism'

instance = NutanixPrism::PrismV40ConfigDomainManagerResourceConfig.new(
  num_vcpus: 3,
  memory_size_bytes: 45,
  data_disk_size_bytes: 23,
  container_ext_ids: null
)
```

