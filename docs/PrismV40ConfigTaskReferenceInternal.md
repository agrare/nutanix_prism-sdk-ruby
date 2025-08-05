# NutanixPrism::PrismV40ConfigTaskReferenceInternal

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **href** | **String** | The URL at which the entity described by the link can be accessed.  | [optional] |
| **rel** | **String** | A name that identifies the relationship of the link to the object that is returned by the URL.  The unique value of \&quot;self\&quot; identifies the URL for the object.  | [optional] |
| **ext_id** | **String** | A globally unique identifier of the task. | [optional][readonly] |

## Example

```ruby
require 'nutanix_prism'

instance = NutanixPrism::PrismV40ConfigTaskReferenceInternal.new(
  href: null,
  rel: null,
  ext_id: QmFzZTY0RW5jb2RlZA&#x3D;&#x3D;:0b2e57b5-209f-4031-a435-7ad83da469aa
)
```

