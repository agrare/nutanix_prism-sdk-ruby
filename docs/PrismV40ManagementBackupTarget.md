# NutanixPrism::PrismV40ManagementBackupTarget

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **tenant_id** | **String** | A globally unique identifier that represents the tenant that owns this entity. The system automatically assigns it, and it and is immutable from an API consumer perspective (some use cases may cause this Id to change - For instance, a use case may require the transfer of ownership of the entity, but these cases are handled automatically on the server).  | [optional][readonly] |
| **ext_id** | **String** | A globally unique identifier of an instance that is suitable for external consumption.  | [optional][readonly] |
| **links** | [**Array&lt;CommonV10ResponseApiLink&gt;**](CommonV10ResponseApiLink.md) | A HATEOAS style link for the response.  Each link contains a user-friendly name identifying the link and an address for retrieving the particular resource.  | [optional][readonly] |
| **location** | [**PrismV40ManagementBackupTargetAllOfLocation**](PrismV40ManagementBackupTargetAllOfLocation.md) |  |  |
| **last_sync_time** | **Time** | Represents the time when the domain manager was last synchronized or copied its  configuration data to the backup target. This field is updated every 30 minutes.  | [optional][readonly] |
| **is_backup_paused** | **Boolean** | Whether the backup is paused on the given cluster or not.  | [optional][readonly] |
| **backup_pause_reason** | **String** | Specifies a reason why the backup might have paused. This will be empty if the isBackupPaused field is false.  | [optional][readonly] |

## Example

```ruby
require 'nutanix_prism'

instance = NutanixPrism::PrismV40ManagementBackupTarget.new(
  tenant_id: d568ff06-a6dc-480f-868c-b85b52f447ba,
  ext_id: 0562e12d-543d-4030-9271-20ba8e72fcb2,
  links: null,
  location: null,
  last_sync_time: 2009-09-23T14:30-07:00,
  is_backup_paused: true,
  backup_pause_reason: The backup is paused due to upgrade in progress. It will be automatically un-paused after upgrade has finished
)
```

