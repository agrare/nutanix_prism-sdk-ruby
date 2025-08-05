# NutanixPrism::PrismV40ConfigAssociationSummary

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **category_id** | **String** | External identifier for the given category that is used across all v4 apis/entities/resources where categories are referenced.&lt;br&gt; The field is in UUID format.&lt;br&gt; A type 4 UUID is generated during category creation.  | [optional] |
| **resource_type** | [**PrismV40ConfigResourceType**](PrismV40ConfigResourceType.md) |  | [optional] |
| **resource_group** | [**PrismV40ConfigResourceGroup**](PrismV40ConfigResourceGroup.md) |  | [optional] |
| **count** | **Integer** | Count of associations of a particular type of entity or policy  | [optional] |

## Example

```ruby
require 'nutanix_prism'

instance = NutanixPrism::PrismV40ConfigAssociationSummary.new(
  category_id: 0a817535-bca1-4e50-9395-f1970ebaa2db,
  resource_type: null,
  resource_group: null,
  count: 44
)
```

