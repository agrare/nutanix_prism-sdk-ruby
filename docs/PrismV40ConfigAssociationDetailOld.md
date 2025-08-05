# NutanixPrism::PrismV40ConfigAssociationDetailOld

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **category_id** | **String** | External identifier for the given category.  | [optional] |
| **resource_type** | [**PrismV40ConfigResourceType**](PrismV40ConfigResourceType.md) |  | [optional] |
| **resource_group** | [**PrismV40ConfigResourceGroup**](PrismV40ConfigResourceGroup.md) |  | [optional] |
| **count** | **Integer** | Denotes the type of a category.&lt;br&gt; There are three types of categories: SYSTEM, INTERNAL, and USER.&lt;br&gt; This field is immutable.  | [optional] |
| **resource_references** | [**Array&lt;PrismV40ConfigReference&gt;**](PrismV40ConfigReference.md) |  | [optional] |

## Example

```ruby
require 'nutanix_prism'

instance = NutanixPrism::PrismV40ConfigAssociationDetailOld.new(
  category_id: null,
  resource_type: null,
  resource_group: null,
  count: 87,
  resource_references: null
)
```

