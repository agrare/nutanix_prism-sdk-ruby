# NutanixPrism::PrismV40ManagementClusterRegistrationSpecRemoteCluster

## Class instance methods

### `openapi_one_of`

Returns the list of classes defined in oneOf.

#### Example

```ruby
require 'nutanix_prism'

NutanixPrism::PrismV40ManagementClusterRegistrationSpecRemoteCluster.openapi_one_of
# =>
# [
#   :'PrismV40ManagementAOSRemoteClusterSpec',
#   :'PrismV40ManagementClusterReference',
#   :'PrismV40ManagementDomainManagerRemoteClusterSpec'
# ]
```

### build

Find the appropriate object from the `openapi_one_of` list and casts the data into it.

#### Example

```ruby
require 'nutanix_prism'

NutanixPrism::PrismV40ManagementClusterRegistrationSpecRemoteCluster.build(data)
# => #<PrismV40ManagementAOSRemoteClusterSpec:0x00007fdd4aab02a0>

NutanixPrism::PrismV40ManagementClusterRegistrationSpecRemoteCluster.build(data_that_doesnt_match)
# => nil
```

#### Parameters

| Name | Type | Description |
| ---- | ---- | ----------- |
| **data** | **Mixed** | data to be matched against the list of oneOf items |

#### Return type

- `PrismV40ManagementAOSRemoteClusterSpec`
- `PrismV40ManagementClusterReference`
- `PrismV40ManagementDomainManagerRemoteClusterSpec`
- `nil` (if no type matches)

