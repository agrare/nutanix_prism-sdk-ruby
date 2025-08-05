# NutanixPrism::PrismV40ConfigCategoryOld

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **tenant_id** | **String** | A globally unique identifier that represents the tenant that owns this entity. The system automatically assigns it, and it and is immutable from an API consumer perspective (some use cases may cause this Id to change - For instance, a use case may require the transfer of ownership of the entity, but these cases are handled automatically on the server).  | [optional][readonly] |
| **ext_id** | **String** | A globally unique identifier of an instance that is suitable for external consumption.  | [optional][readonly] |
| **links** | [**Array&lt;CommonV10ResponseApiLink&gt;**](CommonV10ResponseApiLink.md) | A HATEOAS style link for the response.  Each link contains a user-friendly name identifying the link and an address for retrieving the particular resource.  | [optional][readonly] |
| **fq_name** | **String** | The fully qualified name of this category. It is unique for each category.&lt;br&gt; It is a read-only field. The service constructs it from the name-parentExtId combination. An example of a fqName would be &#x60;Location/Bangalore&#x60;, where &#x60;Location&#x60; is the parent category&#39;s name and &#x60;Bangalore&#x60; is the category name.&lt;br&gt; This field is immutable.&lt;br&gt;  | [optional] |
| **name** | **String** | The short name of this category. It may not be unique for each category.&lt;br&gt; It is a mandatory field that must be specified inside the post/put request  body.&lt;br&gt; This field is immutable.  |  |
| **parent_ext_id** | **String** | The parent category of this category (may be null if this category is not part of a hierarchy).&lt;br&gt; Each category can have at most one parent.&lt;br&gt; A parent cannot be deleted until all the children categories are deleted first.&lt;br&gt; Must be specified inside the post/put request body for child categories (if not specified, the service assumes the category to be a parent category).&lt;br&gt; This field is immutable.  | [optional] |
| **user_specified_name** | **String** | The user-specified name is a string that the user can specify; with syntax and semantics controlled by the user.  The server does not validate this value nor does it enforce the uniqueness or any other constraints.&lt;br&gt; It is the responsibility of the user to ensure that any semantic or syntactic constraints are retained when mutating this field. Unlike the name of the categories, which are immutable, the user name can be changed by the user to meet their needs.  | [optional] |
| **type** | [**PrismV40ConfigCategoryType**](PrismV40ConfigCategoryType.md) |  | [optional] |
| **description** | **String** | A string consisting of the description of the category as defined by the user.  The server does not validate this value nor does it enforce the uniqueness or any other constraints.&lt;br&gt; It is the responsibility of the user to ensure that any semantic or syntactic constraints are retained when mutating this field.  | [optional] |
| **associations** | [**Array&lt;PrismV40ConfigCategoryAssociationSummaryOld&gt;**](PrismV40ConfigCategoryAssociationSummaryOld.md) |  | [optional][readonly] |
| **child_categories** | [**Array&lt;PrismV40ConfigCategorySummaryOld&gt;**](PrismV40ConfigCategorySummaryOld.md) | This attribute contains the list of all the categories for which this category is the parent.&lt;br&gt; The parentExtId attributes of each child category is set as the extId of this category.&lt;br&gt; Note that this list only contains the Summary view of each child category.  | [optional][readonly] |
| **owner_uuid** | **String** | It is a read-only field inserted into category entity at the time of category creation, and which contains the UUID of the user who created this category. It is used for enabling authorization of a particular kind where the user has no access to view/create/update/delete any categories other than the category created by oneself. | [optional] |
| **metadata** | [**Array&lt;CommonV10ConfigKVPair&gt;**](CommonV10ConfigKVPair.md) | Opaque metadata which can be associated to a category.&lt;br&gt; It is a list of key-value pairs.&lt;br&gt; For example, for a category &#39;California/SanJose&#39; we can associate a geographical coordinate based metadata like: {&#39;latitude&#39;: &#39;37.3382° N&#39;, &#39;longitude&#39;: &#39;121.8863° W&#39;}.  The server does not validate this value nor does it enforce the uniqueness or any other constraints. It is the responsibility of the user to ensure that any semantic or syntactic constraints are retained when mutating this field.  | [optional] |

## Example

```ruby
require 'nutanix_prism'

instance = NutanixPrism::PrismV40ConfigCategoryOld.new(
  tenant_id: d568ff06-a6dc-480f-868c-b85b52f447ba,
  ext_id: 0562e12d-543d-4030-9271-20ba8e72fcb2,
  links: null,
  fq_name: null,
  name: null,
  parent_ext_id: b64670aa-36f9-4ac6-b077-dbe101bf727a,
  user_specified_name: null,
  type: null,
  description: null,
  associations: null,
  child_categories: null,
  owner_uuid: 8294b990-0b9a-45d9-80e2-a72b4332bb2f,
  metadata: null
)
```

