# NutanixPrism::PrismV40OperationsBatch

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **tenant_id** | **String** | A globally unique identifier that represents the tenant that owns this entity. The system automatically assigns it, and it and is immutable from an API consumer perspective (some use cases may cause this Id to change - For instance, a use case may require the transfer of ownership of the entity, but these cases are handled automatically on the server).  | [optional][readonly] |
| **ext_id** | **String** | A globally unique identifier of an instance that is suitable for external consumption.  | [optional][readonly] |
| **links** | [**Array&lt;CommonV10ResponseApiLink&gt;**](CommonV10ResponseApiLink.md) | A HATEOAS style link for the response.  Each link contains a user-friendly name identifying the link and an address for retrieving the particular resource.  | [optional][readonly] |
| **name** | **String** | An user friendly name of the batch. | [optional] |
| **start_time** | **Time** | The execution start time of the batch. The value will be in extended ISO-8601 format. For example, start time of 2022-04-23T01:23:45.678+09:00 would imply that the batch started execution at 1:23:45.678  on the 23rd of April 2022. Details around ISO-8601 format can be found at https://www.iso.org/standard/70907.html  | [optional][readonly] |
| **end_time** | **Time** | The completion time of the batch. The value will be in extended ISO-8601 format. For example, end time of 2022-04-23T01:23:45.678+09:00 would imply that the batch completed its execution at 1:23:45.678  on the 23rd of April 2022. Details around ISO-8601 format can be found at https://www.iso.org/standard/70907.html  | [optional][readonly] |
| **size** | **Integer** | The total number of elements submitted for processing in the batch. | [optional] |
| **success_count** | **Integer** | The total number of elements successfully processed in the batch. | [optional] |
| **failed_count** | **Integer** | The total number of elements that failed to be processed in the batch. | [optional] |
| **completion_status** | [**PrismV40OperationsBatchCompletionStatus**](PrismV40OperationsBatchCompletionStatus.md) |  | [optional] |
| **execution_status** | [**PrismV40OperationsBatchExecutionStatus**](PrismV40OperationsBatchExecutionStatus.md) |  | [optional] |
| **should_stop_on_error** | **Boolean** | A flag indicating whether the batch procession should halt or continue when an error response is received from the server during the execution of a batch chunk | [optional] |

## Example

```ruby
require 'nutanix_prism'

instance = NutanixPrism::PrismV40OperationsBatch.new(
  tenant_id: d568ff06-a6dc-480f-868c-b85b52f447ba,
  ext_id: 0562e12d-543d-4030-9271-20ba8e72fcb2,
  links: null,
  name: null,
  start_time: 2009-09-23T14:30-07:00,
  end_time: 2009-09-23T14:30-07:00,
  size: 74,
  success_count: 79,
  failed_count: 22,
  completion_status: null,
  execution_status: null,
  should_stop_on_error: false
)
```

