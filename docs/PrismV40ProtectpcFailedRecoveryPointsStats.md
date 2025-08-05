# NutanixPrism::PrismV40ProtectpcFailedRecoveryPointsStats

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **total_failed_recovery_points** | **Integer** | Count of failed recovery points in last 30 days.  | [optional] |
| **failed_recovery_points** | [**Array&lt;PrismV40ProtectpcFailedRecoveryPointDetails&gt;**](PrismV40ProtectpcFailedRecoveryPointDetails.md) |  | [optional] |

## Example

```ruby
require 'nutanix_prism'

instance = NutanixPrism::PrismV40ProtectpcFailedRecoveryPointsStats.new(
  total_failed_recovery_points: 68,
  failed_recovery_points: null
)
```

