# NutanixPrism::PrismV40ProtectpcBackupTargets

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **cluster_uuid_list** | **Array&lt;String&gt;** | List of PE cluster uuid.  | [optional] |
| **object_store_endpoint_list** | [**Array&lt;PrismV40ProtectpcPcObjectStoreEndpoint&gt;**](PrismV40ProtectpcPcObjectStoreEndpoint.md) |  | [optional] |

## Example

```ruby
require 'nutanix_prism'

instance = NutanixPrism::PrismV40ProtectpcBackupTargets.new(
  cluster_uuid_list: null,
  object_store_endpoint_list: null
)
```

