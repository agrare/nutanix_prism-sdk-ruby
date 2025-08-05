# NutanixPrism::PrismV40ProtectpcPEInfo

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **pe_cluster_id** | **String** | PE cluster uuid. A unique id corresponding to the cluster. | [optional] |
| **pe_name** | **String** | A human redable name of the PE cluster. | [optional] |
| **last_sync_timestamp** | **Integer** | The last sync time signifies the time at which the backup was last synced to PE. This time will be updated every 30min. | [optional] |
| **is_backup_paused** | **Boolean** | Tells whether the backup is paused on the given PE or not. | [optional] |
| **pause_backup_message** | **String** | Tells the reason why the backup might be paused. Will be empty if isBackupPaused field is false. | [optional] |

## Example

```ruby
require 'nutanix_prism'

instance = NutanixPrism::PrismV40ProtectpcPEInfo.new(
  pe_cluster_id: 789e5828-6e9f-4a4b-a7af-818c0fa805bf,
  pe_name: null,
  last_sync_timestamp: 49,
  is_backup_paused: true,
  pause_backup_message: null
)
```

