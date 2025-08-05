# NutanixPrism::PrismV40ConfigTask

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **ext_id** | **String** | A globally unique identifier of a task. | [optional][readonly] |
| **operation** | **String** | The operation name being tracked by the task. | [optional][readonly] |
| **operation_description** | **String** | Description of the operation being tracked by the task. | [optional][readonly] |
| **parent_task** | [**PrismV40ConfigTaskReferenceInternal**](PrismV40ConfigTaskReferenceInternal.md) |  | [optional] |
| **created_time** | **Time** | UTC date and time in RFC-3339 format when the task was created. | [optional][readonly] |
| **started_time** | **Time** | UTC date and time in RFC-3339 format when the task was started. | [optional][readonly] |
| **completed_time** | **Time** | UTC date and time in RFC-3339 format when the task was completed. | [optional][readonly] |
| **status** | [**PrismV40ConfigTaskStatus**](PrismV40ConfigTaskStatus.md) |  | [optional] |
| **progress_percentage** | **Integer** | Task progress expressed as a percentage. | [optional][readonly] |
| **entities_affected** | [**Array&lt;PrismV40ConfigEntityReference&gt;**](PrismV40ConfigEntityReference.md) | Reference to entities associated with the task. | [optional][readonly] |
| **sub_tasks** | [**Array&lt;PrismV40ConfigTaskReferenceInternal&gt;**](PrismV40ConfigTaskReferenceInternal.md) | Reference to tasks spawned as children of the current task. The task get response would contain a limited number of subtask references. To get the entire list of subtasks for a task, use the parent task filter in the task list API. | [optional][readonly] |
| **sub_steps** | [**Array&lt;PrismV40ConfigTaskStep&gt;**](PrismV40ConfigTaskStep.md) | List of steps completed as part of the task. | [optional][readonly] |
| **is_cancelable** | **Boolean** | Signifies if the task can be cancelled. | [optional][readonly] |
| **owned_by** | [**PrismV40ConfigOwnerReference**](PrismV40ConfigOwnerReference.md) |  | [optional] |
| **completion_details** | [**Array&lt;CommonV10ConfigKVPair&gt;**](CommonV10ConfigKVPair.md) | Additional details on the task to aid the user with further actions post completion of the task. | [optional][readonly] |
| **error_messages** | [**Array&lt;PrismV40ErrorAppMessage&gt;**](PrismV40ErrorAppMessage.md) | Error details explaining a task failure. These would be populated only in the case of task failures. | [optional][readonly] |
| **legacy_error_message** | **String** | Provides an error message in the absence of a well-defined error message for the tasks created through legacy APIs. | [optional][readonly] |
| **warnings** | [**Array&lt;PrismV40ErrorAppMessage&gt;**](PrismV40ErrorAppMessage.md) | Warning messages to alert the user of issues which did not directly cause task failure. These can be populated for any task. | [optional][readonly] |
| **last_updated_time** | **Time** | UTC date and time in RFC-3339 format when the task was last updated. | [optional][readonly] |
| **cluster_ext_ids** | **Array&lt;String&gt;** | List of globally unique identifiers for clusters associated with the task or any of its subtasks. | [optional][readonly] |
| **root_task** | [**PrismV40ConfigTaskReferenceInternal**](PrismV40ConfigTaskReferenceInternal.md) |  | [optional] |
| **is_background_task** | **Boolean** | Signifies if the task is a background task or not. | [optional][readonly] |
| **number_of_subtasks** | **Integer** | Number of tasks spawned as children of the current task. | [optional][readonly] |
| **number_of_entities_affected** | **Integer** | Number of entities associated with the task. | [optional][readonly] |

## Example

```ruby
require 'nutanix_prism'

instance = NutanixPrism::PrismV40ConfigTask.new(
  ext_id: QmFzZTY0RW5jb2RlZA&#x3D;&#x3D;:86114933-1b11-4c4f-bb21-b8b7075e1044,
  operation: kVmCreate,
  operation_description: Create VM,
  parent_task: null,
  created_time: 2009-09-23T14:30-07:00,
  started_time: 2009-09-23T14:30-07:00,
  completed_time: 2009-09-23T14:30-07:00,
  status: null,
  progress_percentage: 90,
  entities_affected: null,
  sub_tasks: null,
  sub_steps: null,
  is_cancelable: true,
  owned_by: null,
  completion_details: null,
  error_messages: null,
  legacy_error_message: Setting Credential Guard for a VM with a GPU is not supported,
  warnings: null,
  last_updated_time: 2009-09-23T14:30-07:00,
  cluster_ext_ids: null,
  root_task: null,
  is_background_task: true,
  number_of_subtasks: 78,
  number_of_entities_affected: 79
)
```

