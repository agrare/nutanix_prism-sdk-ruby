# NutanixPrism::PrismV40ConfigBootstrapConfig

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **cloud_init_config** | [**Array&lt;VmmV40AhvConfigCloudInit&gt;**](VmmV40AhvConfigCloudInit.md) | List of cloud-init commands required to bootstrap the domain manager (Prism Central) cluster on a startup. | [optional] |
| **environment_info** | [**PrismV40ConfigEnvironmentInfo**](PrismV40ConfigEnvironmentInfo.md) |  | [optional] |

## Example

```ruby
require 'nutanix_prism'

instance = NutanixPrism::PrismV40ConfigBootstrapConfig.new(
  cloud_init_config: null,
  environment_info: null
)
```

