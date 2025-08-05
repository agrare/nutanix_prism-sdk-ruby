# NutanixPrism::ClustermgmtV40ConfigClusterNetwork

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **external_address** | [**CommonV10ConfigIPAddress**](CommonV10ConfigIPAddress.md) |  | [optional] |
| **name_servers** | [**Array&lt;CommonV10ConfigIPAddressOrFQDN&gt;**](CommonV10ConfigIPAddressOrFQDN.md) | List of name servers on a cluster. This is part of payload for both cluster create &amp; update operations. For create operation, only ipv4 address / fqdn values are supported currently. | [optional] |
| **ntp_servers** | [**Array&lt;CommonV10ConfigIPAddressOrFQDN&gt;**](CommonV10ConfigIPAddressOrFQDN.md) | List of NTP servers on a cluster. This is part of payload for both cluster create &amp; update operations. For create operation, only ipv4 address / fqdn values are supported currently. | [optional] |
| **fqdn** | **String** | Cluster fully qualified domain name. This is part of payload for cluster update operation only. | [optional][readonly] |

## Example

```ruby
require 'nutanix_prism'

instance = NutanixPrism::ClustermgmtV40ConfigClusterNetwork.new(
  external_address: null,
  name_servers: null,
  ntp_servers: null,
  fqdn: www.example-corp.com
)
```

