# NutanixPrism::CommonV10ConfigBasicAuth

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **username** | **String** | Username required for the basic auth scheme. As per [RFC 2617](https://datatracker.ietf.org/doc/html/rfc2617) usernames might be case sensitive.  |  |
| **password** | **String** | Password required for the basic auth scheme.  |  |

## Example

```ruby
require 'nutanix_prism'

instance = NutanixPrism::CommonV10ConfigBasicAuth.new(
  username: test-user,
  password: ***********
)
```

