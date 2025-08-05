# NutanixPrism::PrismV40ConfigBaseNetwork

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **default_gateway** | [**CommonV10ConfigIPAddressOrFQDN**](CommonV10ConfigIPAddressOrFQDN.md) |  |  |
| **subnet_mask** | [**CommonV10ConfigIPAddressOrFQDN**](CommonV10ConfigIPAddressOrFQDN.md) |  |  |
| **ip_ranges** | [**Array&lt;CommonV10ConfigIpRange&gt;**](CommonV10ConfigIpRange.md) | Range of IPs used for Prism Central network setup. |  |

## Example

```ruby
require 'nutanix_prism'

instance = NutanixPrism::PrismV40ConfigBaseNetwork.new(
  default_gateway: null,
  subnet_mask: null,
  ip_ranges: null
)
```

