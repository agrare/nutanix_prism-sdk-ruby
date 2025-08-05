# NutanixPrism::PrismV40ManagementAccessKeyCredentials

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **access_key_id** | **String** | Access key Id for the object store provided for backup target. |  |
| **secret_access_key** | **String** | Secret access key for the object store provided for backup target.  |  |

## Example

```ruby
require 'nutanix_prism'

instance = NutanixPrism::PrismV40ManagementAccessKeyCredentials.new(
  access_key_id: AKIAZ26UIJS6DRKHPPF4,
  secret_access_key: L1feKeOuNErB0SCULU1XrGKS5gWAGb1RQp/Lxc3y
)
```

