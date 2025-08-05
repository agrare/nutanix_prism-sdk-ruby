# NutanixPrism::PrismV40ManagementBackupPolicy

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **rpo_in_minutes** | **Integer** | RPO interval in minutes at which the backup will be taken  |  |

## Example

```ruby
require 'nutanix_prism'

instance = NutanixPrism::PrismV40ManagementBackupPolicy.new(
  rpo_in_minutes: 86
)
```

