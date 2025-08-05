# NutanixPrism::PrismV40ProtectpcRecoveryStatus

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **recovery_state** | **String** | Recovery state of recovery task. Possible values could be IDFDataRestore, WaitForProcessesToReconcile.  | [optional] |
| **recovery_state_title** | **String** | Recovery state title, the message that appears to the user.  | [optional] |
| **overall_completion_percentage** | **Integer** | Overall completion percentage of task.  | [optional] |

## Example

```ruby
require 'nutanix_prism'

instance = NutanixPrism::PrismV40ProtectpcRecoveryStatus.new(
  recovery_state: null,
  recovery_state_title: null,
  overall_completion_percentage: null
)
```

