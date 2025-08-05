# NutanixPrism::PrismV40ConfigExternalNetwork

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **default_gateway** | [**CommonV10ConfigIPAddressOrFQDN**](CommonV10ConfigIPAddressOrFQDN.md) |  |  |
| **subnet_mask** | [**CommonV10ConfigIPAddressOrFQDN**](CommonV10ConfigIPAddressOrFQDN.md) |  |  |
| **ip_ranges** | [**Array&lt;CommonV10ConfigIpRange&gt;**](CommonV10ConfigIpRange.md) | Range of IPs used for Prism Central network setup. |  |
| **network_ext_id** | **String** | The network external identifier to which Domain Manager (Prism Central) is to be deployed or is already configured. |  |

## Example

```ruby
require 'nutanix_prism'

instance = NutanixPrism::PrismV40ConfigExternalNetwork.new(
  default_gateway: null,
  subnet_mask: null,
  ip_ranges: null,
  network_ext_id: bb63edde-0ea7-4bde-8924-daf7a3ec7717
)
```

