# NutanixPrism::PrismV40ConfigCategory

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **tenant_id** | **String** | A globally unique identifier that represents the tenant that owns this entity. The system automatically assigns it, and it and is immutable from an API consumer perspective (some use cases may cause this Id to change - For instance, a use case may require the transfer of ownership of the entity, but these cases are handled automatically on the server).  | [optional][readonly] |
| **ext_id** | **String** | A globally unique identifier of an instance that is suitable for external consumption.  | [optional][readonly] |
| **links** | [**Array&lt;CommonV10ResponseApiLink&gt;**](CommonV10ResponseApiLink.md) | A HATEOAS style link for the response.  Each link contains a user-friendly name identifying the link and an address for retrieving the particular resource.  | [optional][readonly] |
| **key** | **String** | The key of a category when it is represented in &#x60;key:value&#x60; format.  Constraints applicable when field is given in the payload during create and update: * A string of maxlength of 64 * Character at the start cannot be &#x60;$&#x60; * Character &#x60;/&#x60; is not allowed anywhere  It is a mandatory field in the payload of &#x60;createCategory&#x60; and &#x60;updateCategoryById&#x60; APIs.&lt;br&gt; This field can&#39;t be updated through &#x60;updateCategoryById&#x60; API.  |  |
| **value** | **String** | The value of a category when it is represented in &#x60;key:value&#x60; format.  Constraints applicable when the field is given in the payload during create and update: * A string of max length 64 * Character at the start cannot be &#x60;$&#x60; * Character &#x60;/&#x60; is not allowed anywhere  It is a mandatory input field in the payload of &#x60;createCategory&#x60; and &#x60;updateCategoryById&#x60; APIs.&lt;br&gt; This field can be updated through &#x60;updateCategoryById&#x60; API.&lt;br&gt; Updating the value will not change the extId of the category.  |  |
| **type** | [**PrismV40ConfigCategoryType**](PrismV40ConfigCategoryType.md) |  | [optional] |
| **description** | **String** | A string consisting of the description of the category as defined by the user.&lt;br&gt; Description can be optionally provided in the payload of &#x60;createCategory&#x60; and &#x60;updateCategoryById&#x60; APIs.&lt;br&gt; Description field can be updated through &#x60;updateCategoryById&#x60; API.&lt;br&gt; The server does not validate this value nor does it enforce the uniqueness or any other constraints.&lt;br&gt; It is the responsibility of the user to ensure that any semantic or syntactic constraints are retained when mutating this field.  | [optional] |
| **owner_uuid** | **String** | This field contains the UUID of a user who owns the category.&lt;br&gt; This field will be ignored if given in the payload of &#x60;createCategory&#x60; API. Hence, when a category is created, the logged-in user automatically becomes the owner of the category.&lt;br&gt; This field can be updated through &#x60;updateCategoryById&#x60; API, in which case, should be provided, UUID of a valid user is present in the system.&lt;br&gt; Validity of the user UUID can be checked by invoking the API: authn/users/{extId} in the &#39;Identity and Access Management&#39; or &#39;IAM&#39; namespace.&lt;br&gt; It is used for enabling RBAC access to self-owned categories.  | [optional] |
| **associations** | [**Array&lt;PrismV40ConfigAssociationSummary&gt;**](PrismV40ConfigAssociationSummary.md) | This field gives basic information about resources that are associated with the category.&lt;br&gt; The results present under this field summarize the counts of various kinds of resources associated with the category.&lt;br&gt; For more detailed information about the UUIDs of the resources, please look into the field &#x60;detailedAssociations&#x60;.&lt;br&gt; This field will be ignored, if given in the payload of &#x60;updateCategoryById&#x60; or &#x60;createCategory&#x60; APIs.&lt;br&gt; This field will not be present by default in &#x60;listCategories&#x60; API, unless the parameter $expand&#x3D;associations is present in the URL.  | [optional][readonly] |
| **detailed_associations** | [**Array&lt;PrismV40ConfigAssociationDetail&gt;**](PrismV40ConfigAssociationDetail.md) | This field gives detailed information about the resources which are associated with the category.&lt;br&gt; The results present under this field contain the UUIDs of the entities and policies of various kinds associated with the category.&lt;br&gt; This field will be ignored, if given in the payload of &#x60;updateCategoryById&#x60; or &#x60;createCategory&#x60; APIs.&lt;br&gt; This field will not be present by default in &#x60;listCategories&#x60; or &#x60;getCategoryById&#x60; APIs, unless the parameter $expand&#x3D;detailedAssociations is present in the URL.  | [optional][readonly] |

## Example

```ruby
require 'nutanix_prism'

instance = NutanixPrism::PrismV40ConfigCategory.new(
  tenant_id: d568ff06-a6dc-480f-868c-b85b52f447ba,
  ext_id: 0562e12d-543d-4030-9271-20ba8e72fcb2,
  links: null,
  key: AvailabilityZone,
  value: APAC,
  type: null,
  description: This category is meant to be used to enforce policies specific to availability zones.,
  owner_uuid: 0425a23e-4ea3-45d2-8402-928bd957be8b,
  associations: null,
  detailed_associations: null
)
```

