# NutanixPrism::CommonV10ConfigIPv4Address

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **value** | **String** | The IPv4 address of the host.  |  |
| **prefix_length** | **Integer** | The prefix length of the network to which this host IPv4 address belongs.  | [optional][default to 32] |

## Example

```ruby
require 'nutanix_prism'

instance = NutanixPrism::CommonV10ConfigIPv4Address.new(
  value: 167.125.234.35,
  prefix_length: null
)
```

