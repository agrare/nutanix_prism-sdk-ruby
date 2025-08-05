# NutanixPrism::PrismV40ProtectpcPcvmRestoreFile

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **file_path** | **String** | Path of the file to be restored.  | [optional] |
| **file_content** | **String** | Contents of the file to be restored.  | [optional] |
| **is_encrypted** | **Boolean** | Whether the file is encrypted.  | [optional] |
| **key_id** | **String** |  | [optional] |
| **encryption_version** | **String** |  | [optional] |

## Example

```ruby
require 'nutanix_prism'

instance = NutanixPrism::PrismV40ProtectpcPcvmRestoreFile.new(
  file_path: null,
  file_content: null,
  is_encrypted: false,
  key_id: null,
  encryption_version: null
)
```

