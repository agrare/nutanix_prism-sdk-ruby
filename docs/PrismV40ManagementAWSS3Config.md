# NutanixPrism::PrismV40ManagementAWSS3Config

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **bucket_name** | **String** | The bucket name of the object store endpoint where backup data of domain manager is to be stored.  |  |
| **region** | **String** | The region name of the object store endpoint where backup data of domain manager is stored.  | [optional][default to &#39;us-east-1&#39;] |
| **credentials** | [**PrismV40ManagementAccessKeyCredentials**](PrismV40ManagementAccessKeyCredentials.md) |  | [optional] |

## Example

```ruby
require 'nutanix_prism'

instance = NutanixPrism::PrismV40ManagementAWSS3Config.new(
  bucket_name: pc-bucket-name,
  region: null,
  credentials: null
)
```

