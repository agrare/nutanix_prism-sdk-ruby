# NutanixPrism::PrismV40ProtectpcBackupTargetsInfo

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **pe_info_list** | [**Array&lt;PrismV40ProtectpcPEInfo&gt;**](PrismV40ProtectpcPEInfo.md) |  | [optional] |
| **object_store_endpoint_info_list** | [**Array&lt;PrismV40ProtectpcObjectStoreEndpointInfo&gt;**](PrismV40ProtectpcObjectStoreEndpointInfo.md) |  | [optional] |

## Example

```ruby
require 'nutanix_prism'

instance = NutanixPrism::PrismV40ProtectpcBackupTargetsInfo.new(
  pe_info_list: null,
  object_store_endpoint_info_list: null
)
```

