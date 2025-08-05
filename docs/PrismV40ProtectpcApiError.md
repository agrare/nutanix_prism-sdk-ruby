# NutanixPrism::PrismV40ProtectpcApiError

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **error_message_list** | **Array&lt;String&gt;** | The error message field where the error response will be put. | [optional] |
| **error_type** | **String** | The type of error, like INVALID_INPUT, INTERNAL_SERVER_ERROR, etc. | [optional] |

## Example

```ruby
require 'nutanix_prism'

instance = NutanixPrism::PrismV40ProtectpcApiError.new(
  error_message_list: null,
  error_type: null
)
```

