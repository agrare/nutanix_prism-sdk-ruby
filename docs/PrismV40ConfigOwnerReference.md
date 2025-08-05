# NutanixPrism::PrismV40ConfigOwnerReference

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **ext_id** | **String** | A globally unique identifier of the task owner. | [optional][readonly] |
| **name** | **String** | Username of the task owner. | [optional][readonly] |

## Example

```ruby
require 'nutanix_prism'

instance = NutanixPrism::PrismV40ConfigOwnerReference.new(
  ext_id: c9a10a62-5724-4b67-8a7d-2d8bdf6365d8,
  name: Test User
)
```

