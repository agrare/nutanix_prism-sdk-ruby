# NutanixPrism::CommonV10ConfigIPv6Address

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **value** | **String** | The IPv6 address of the host.  |  |
| **prefix_length** | **Integer** | The prefix length of the network to which this host IPv6 address belongs.  | [optional][default to 128] |

## Example

```ruby
require 'nutanix_prism'

instance = NutanixPrism::CommonV10ConfigIPv6Address.new(
  value: 839c:6c4e:ae35:c0ba:4eae:b6ec:9eaa:f162,
  prefix_length: null
)
```

