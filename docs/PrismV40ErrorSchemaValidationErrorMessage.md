# NutanixPrism::PrismV40ErrorSchemaValidationErrorMessage

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **location** | **String** | The part of the request that failed validation. Validation can fail for path, query parameters, and request body. | [optional] |
| **message** | **String** | The detailed message for the validation error. | [optional] |
| **attribute_path** | **String** | The path of the attribute that failed validation in the schema. | [optional] |

## Example

```ruby
require 'nutanix_prism'

instance = NutanixPrism::PrismV40ErrorSchemaValidationErrorMessage.new(
  location: null,
  message: null,
  attribute_path: null
)
```

