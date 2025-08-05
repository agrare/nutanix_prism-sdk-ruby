# NutanixPrism::PrismV40ConfigEntityReference

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **ext_id** | **String** | A globally unique identifier of the entity. | [optional][readonly] |
| **rel** | **String** | Entity type identified as &#39;namespace:module[:submodule]:entityType&#39;. For example - vmm:ahv:vm, where vmm is the namepsace, ahv is the module and vm is the entitytype. | [optional][readonly] |
| **name** | **String** | Name of the entity. | [optional][readonly] |

## Example

```ruby
require 'nutanix_prism'

instance = NutanixPrism::PrismV40ConfigEntityReference.new(
  ext_id: 7ccae44f-d067-4d49-a4d0-7409e2455894,
  rel: vmm:ahv:config:vm,
  name: Test VM
)
```

