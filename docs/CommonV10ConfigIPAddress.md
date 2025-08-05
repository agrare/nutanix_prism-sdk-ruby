# NutanixPrism::CommonV10ConfigIPAddress

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **ipv4** | [**CommonV10ConfigIPv4Address**](CommonV10ConfigIPv4Address.md) |  | [optional] |
| **ipv6** | [**CommonV10ConfigIPv6Address**](CommonV10ConfigIPv6Address.md) |  | [optional] |

## Example

```ruby
require 'nutanix_prism'

instance = NutanixPrism::CommonV10ConfigIPAddress.new(
  ipv4: null,
  ipv6: null
)
```

