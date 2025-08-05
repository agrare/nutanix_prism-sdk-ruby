# NutanixPrism::PrismV40ConfigDomainManagerClusterConfig

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **should_enable_lockdown_mode** | **Boolean** | A boolean value indicating whether to enable lockdown mode for a cluster. | [optional] |
| **build_info** | [**ClustermgmtV40ConfigBuildInfo**](ClustermgmtV40ConfigBuildInfo.md) |  |  |
| **name** | **String** | Name of the domain manager (Prism Central). |  |
| **size** | [**PrismV40ConfigSize**](PrismV40ConfigSize.md) |  |  |
| **bootstrap_config** | [**PrismV40ConfigBootstrapConfig**](PrismV40ConfigBootstrapConfig.md) |  | [optional] |
| **credentials** | [**Array&lt;CommonV10ConfigBasicAuth&gt;**](CommonV10ConfigBasicAuth.md) | The credentials consist of a username and password for a particular user like admin. Users can pass the credentials of admin users currently which will be configured in the create domain manager operation. | [optional] |
| **resource_config** | [**PrismV40ConfigDomainManagerResourceConfig**](PrismV40ConfigDomainManagerResourceConfig.md) |  | [optional] |

## Example

```ruby
require 'nutanix_prism'

instance = NutanixPrism::PrismV40ConfigDomainManagerClusterConfig.new(
  should_enable_lockdown_mode: false,
  build_info: null,
  name: pc_nutanix_01,
  size: null,
  bootstrap_config: null,
  credentials: null,
  resource_config: null
)
```

