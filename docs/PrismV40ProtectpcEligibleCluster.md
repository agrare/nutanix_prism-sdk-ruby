# NutanixPrism::PrismV40ProtectpcEligibleCluster

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **cluster_uuid** | **String** | Uuid of the eligible PE(cluster).  | [optional] |
| **cluster_name** | **String** | Name of the eligible PE(cluster).  | [optional] |
| **is_hosting_pe** | **Boolean** | Whether the candidate PE was hosting PC.  | [optional] |
| **backed_up_entities_count_supported** | **Integer** | The amount of entities which can be backed up to the PE from PC.  | [optional] |

## Example

```ruby
require 'nutanix_prism'

instance = NutanixPrism::PrismV40ProtectpcEligibleCluster.new(
  cluster_uuid: 26966431-924f-4466-b397-dd565a3a3873,
  cluster_name: null,
  is_hosting_pe: true,
  backed_up_entities_count_supported: 5
)
```

