# NutanixPrism::PrismV40ProtectpcPcObjectStoreEndpoint

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **endpoint_address** | **String** | The endpoint address of the object store where backup data of Prism Central is present.  | [optional] |
| **endpoint_flavour** | [**PrismV40ProtectpcPcEndpointFlavour**](PrismV40ProtectpcPcEndpointFlavour.md) |  | [optional] |
| **endpoint_credentials** | [**PrismV40ProtectpcPcEndpointCredentials**](PrismV40ProtectpcPcEndpointCredentials.md) |  | [optional] |
| **rpo_seconds** | **Integer** | A RPO value in seconds to be configured.  | [optional] |
| **ip_address_or_domain** | **String** | The ip address or domain of the object store endpoint where backup data of Prism Central is stored.  | [optional] |
| **port** | **String** | The port of the object store endpoint where backup data of Prism Central is stored.  | [optional] |
| **bucket** | **String** | The bucket name of the object store endpoint where backup data of Prism Central is stored.  | [optional] |
| **region** | **String** | The region name of the object store endpoint where backup data of Prism Central is stored.  | [optional][default to &#39;us-east-1&#39;] |
| **skip_tls** | **Boolean** | Skip the verification of TLS certificates during communication with object store endpoint.  | [optional][default to false] |
| **backup_retention_days** | **Integer** | Retention days configured for backup in Object Store.      | [optional][default to 31] |

## Example

```ruby
require 'nutanix_prism'

instance = NutanixPrism::PrismV40ProtectpcPcObjectStoreEndpoint.new(
  endpoint_address: null,
  endpoint_flavour: null,
  endpoint_credentials: null,
  rpo_seconds: 52,
  ip_address_or_domain: null,
  port: null,
  bucket: null,
  region: null,
  skip_tls: null,
  backup_retention_days: null
)
```

