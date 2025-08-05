# NutanixPrism::PrismV40ProtectpcFailedRecoveryPointDetails

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **recovery_point_timestamp** | **Integer** | Timestamp at which backup failed for defined object store.  | [optional] |
| **rpo_seconds** | **Integer** | A RPO value in seconds to be configured.  | [optional] |
| **message** | **String** | Failure reason because of which backup failed for that particular timestamp.  | [optional] |

## Example

```ruby
require 'nutanix_prism'

instance = NutanixPrism::PrismV40ProtectpcFailedRecoveryPointDetails.new(
  recovery_point_timestamp: 85,
  rpo_seconds: 62,
  message: null
)
```

