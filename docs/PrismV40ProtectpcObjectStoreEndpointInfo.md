# NutanixPrism::PrismV40ProtectpcObjectStoreEndpointInfo

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **object_store_endpoint** | [**PrismV40ProtectpcPcObjectStoreEndpoint**](PrismV40ProtectpcPcObjectStoreEndpoint.md) |  | [optional] |
| **last_sync_timestamp** | **Integer** | The last sync time signifies the time at which the backup was last synced to PE. This time will be updated every 30min. | [optional] |
| **is_backup_paused** | **Boolean** | Tells whether the backup is paused on the given PE or not. | [optional] |
| **pause_backup_message** | **String** | Tells the reason why the backup might be paused. Will be empty if isBackupPaused field is false. | [optional] |
| **entity_id** | **String** | A unique id corresponding to the object store. | [optional] |

## Example

```ruby
require 'nutanix_prism'

instance = NutanixPrism::PrismV40ProtectpcObjectStoreEndpointInfo.new(
  object_store_endpoint: null,
  last_sync_timestamp: 40,
  is_backup_paused: false,
  pause_backup_message: null,
  entity_id: 69df8bbf-db7e-4884-b8e0-4dd13acab811
)
```

