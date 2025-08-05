# NutanixPrism::PrismV40ProtectpcReplicaInfo

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **pe_cluster_ip_list** | **Array&lt;String&gt;** |  | [optional] |
| **pe_cluster_id** | **String** | PE cluster uuid. A unique id corresponding to the cluster. | [optional] |
| **backup_uuid** | **String** | BackupUuid for the particular backup for which recovery is triggered.  | [optional] |
| **object_store_endpoint** | [**PrismV40ProtectpcPcObjectStoreEndpoint**](PrismV40ProtectpcPcObjectStoreEndpoint.md) |  | [optional] |

## Example

```ruby
require 'nutanix_prism'

instance = NutanixPrism::PrismV40ProtectpcReplicaInfo.new(
  pe_cluster_ip_list: null,
  pe_cluster_id: null,
  backup_uuid: null,
  object_store_endpoint: null
)
```

