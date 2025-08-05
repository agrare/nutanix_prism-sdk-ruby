# NutanixPrism::VmmV40AhvConfigCloudInit

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **datasource_type** | [**VmmV40AhvConfigCloudInitDataSourceType**](VmmV40AhvConfigCloudInitDataSourceType.md) |  | [optional] |
| **metadata** | **String** | The contents of the meta_data configuration for cloud-init. This can be formatted as YAML or JSON. The value must be base64 encoded. | [optional] |
| **cloud_init_script** | [**VmmV40AhvConfigCloudInitCloudInitScript**](VmmV40AhvConfigCloudInitCloudInitScript.md) |  | [optional] |

## Example

```ruby
require 'nutanix_prism'

instance = NutanixPrism::VmmV40AhvConfigCloudInit.new(
  datasource_type: null,
  metadata: null,
  cloud_init_script: null
)
```

