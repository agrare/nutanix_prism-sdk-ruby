# NutanixPrism::PrismV40ManagementClusterReference

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **ext_id** | **String** | Cluster UUID of a remote cluster. |  |
| **name** | **String** | Name of the cluster. | [optional][readonly] |

## Example

```ruby
require 'nutanix_prism'

instance = NutanixPrism::PrismV40ManagementClusterReference.new(
  ext_id: 5f9c6fef-a851-439c-a150-58f8b76e074c,
  name: null
)
```

