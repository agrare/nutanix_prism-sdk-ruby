# NutanixPrism::PrismV40ConfigDomainManagerNetwork

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **external_address** | [**CommonV10ConfigIPAddress**](CommonV10ConfigIPAddress.md) |  | [optional] |
| **name_servers** | [**Array&lt;CommonV10ConfigIPAddressOrFQDN&gt;**](CommonV10ConfigIPAddressOrFQDN.md) | List of name servers on a cluster. This is part of payload for both cluster create &amp; update operations. For create operation, only ipv4 address / fqdn values are supported currently. |  |
| **ntp_servers** | [**Array&lt;CommonV10ConfigIPAddressOrFQDN&gt;**](CommonV10ConfigIPAddressOrFQDN.md) | List of NTP servers on a cluster. This is part of payload for both cluster create &amp; update operations. For create operation, only ipv4 address / fqdn values are supported currently. |  |
| **fqdn** | **String** | Cluster fully qualified domain name. This is part of payload for cluster update operation only. | [optional][readonly] |
| **internal_networks** | [**Array&lt;PrismV40ConfigBaseNetwork&gt;**](PrismV40ConfigBaseNetwork.md) | This configuration is used to internally manage Prism Central network. | [optional] |
| **external_networks** | [**Array&lt;PrismV40ConfigExternalNetwork&gt;**](PrismV40ConfigExternalNetwork.md) | This configuration is used to manage Prism Central. |  |

## Example

```ruby
require 'nutanix_prism'

instance = NutanixPrism::PrismV40ConfigDomainManagerNetwork.new(
  external_address: null,
  name_servers: null,
  ntp_servers: null,
  fqdn: www.example-corp.com,
  internal_networks: null,
  external_networks: null
)
```

