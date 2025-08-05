# NutanixPrism::PrismV40ManagementObjectStoreLocation

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **provider_config** | [**PrismV40ManagementAWSS3Config**](PrismV40ManagementAWSS3Config.md) |  |  |
| **backup_policy** | [**PrismV40ManagementBackupPolicy**](PrismV40ManagementBackupPolicy.md) |  | [optional] |

## Example

```ruby
require 'nutanix_prism'

instance = NutanixPrism::PrismV40ManagementObjectStoreLocation.new(
  provider_config: null,
  backup_policy: null
)
```

