---
editable: false
sourcePath: en/_api-ref-grpc/loadbalancer/v1/api-ref/grpc/TargetGroup/create.md
---

# Network Load Balancer API, gRPC: TargetGroupService.Create

Creates a target group in the specified folder and adds the specified targets to it.

## gRPC request

**rpc Create ([CreateTargetGroupRequest](#yandex.cloud.loadbalancer.v1.CreateTargetGroupRequest)) returns ([operation.Operation](#yandex.cloud.operation.Operation))**

## CreateTargetGroupRequest {#yandex.cloud.loadbalancer.v1.CreateTargetGroupRequest}

```json
{
  "folder_id": "string",
  "name": "string",
  "description": "string",
  "labels": "string",
  "region_id": "string",
  "targets": [
    {
      "subnet_id": "string",
      "address": "string"
    }
  ]
}
```

#|
||Field | Description ||
|| folder_id | **string**

Required field. ID of the folder to list target groups in.
To get the folder ID, use a [TargetGroupService.List](/docs/network-load-balancer/api-ref/grpc/TargetGroup/list#List) request. ||
|| name | **string**

Name of the target group.
The name must be unique within the folder. ||
|| description | **string**

Description of the target group. ||
|| labels | **string**

Resource labels as `` key:value `` pairs. ||
|| region_id | **string**

ID of the availability zone where the target group resides. ||
|| targets[] | **[Target](#yandex.cloud.loadbalancer.v1.Target)**

List of targets within the target group. ||
|#

## Target {#yandex.cloud.loadbalancer.v1.Target}

A Target resource. For more information, see [Target groups and resources](/docs/network-load-balancer/concepts/target-resources).

#|
||Field | Description ||
|| subnet_id | **string**

ID of the subnet that targets are connected to.
All targets in the target group must be connected to the same subnet within a single availability zone. ||
|| address | **string**

IP address of the target. ||
|#

## operation.Operation {#yandex.cloud.operation.Operation}

```json
{
  "id": "string",
  "description": "string",
  "created_at": "google.protobuf.Timestamp",
  "created_by": "string",
  "modified_at": "google.protobuf.Timestamp",
  "done": "bool",
  "metadata": {
    "target_group_id": "string"
  },
  // Includes only one of the fields `error`, `response`
  "error": "google.rpc.Status",
  "response": {
    "id": "string",
    "folder_id": "string",
    "created_at": "google.protobuf.Timestamp",
    "name": "string",
    "description": "string",
    "labels": "string",
    "region_id": "string",
    "targets": [
      {
        "subnet_id": "string",
        "address": "string"
      }
    ]
  }
  // end of the list of possible fields
}
```

An Operation resource. For more information, see [Operation](/docs/api-design-guide/concepts/operation).

#|
||Field | Description ||
|| id | **string**

ID of the operation. ||
|| description | **string**

Description of the operation. 0-256 characters long. ||
|| created_at | **[google.protobuf.Timestamp](https://developers.google.com/protocol-buffers/docs/reference/google.protobuf#timestamp)**

Creation timestamp. ||
|| created_by | **string**

ID of the user or service account who initiated the operation. ||
|| modified_at | **[google.protobuf.Timestamp](https://developers.google.com/protocol-buffers/docs/reference/google.protobuf#timestamp)**

The time when the Operation resource was last modified. ||
|| done | **bool**

If the value is `false`, it means the operation is still in progress.
If `true`, the operation is completed, and either `error` or `response` is available. ||
|| metadata | **[CreateTargetGroupMetadata](#yandex.cloud.loadbalancer.v1.CreateTargetGroupMetadata)**

Service-specific metadata associated with the operation.
It typically contains the ID of the target resource that the operation is performed on.
Any method that returns a long-running operation should document the metadata type, if any. ||
|| error | **[google.rpc.Status](https://cloud.google.com/tasks/docs/reference/rpc/google.rpc#status)**

The error result of the operation in case of failure or cancellation.

Includes only one of the fields `error`, `response`.

The operation result.
If `done == false` and there was no failure detected, neither `error` nor `response` is set.
If `done == false` and there was a failure detected, `error` is set.
If `done == true`, exactly one of `error` or `response` is set. ||
|| response | **[TargetGroup](#yandex.cloud.loadbalancer.v1.TargetGroup)**

The normal response of the operation in case of success.
If the original method returns no data on success, such as Delete,
the response is [google.protobuf.Empty](https://developers.google.com/protocol-buffers/docs/reference/google.protobuf#google.protobuf.Empty).
If the original method is the standard Create/Update,
the response should be the target resource of the operation.
Any method that returns a long-running operation should document the response type, if any.

Includes only one of the fields `error`, `response`.

The operation result.
If `done == false` and there was no failure detected, neither `error` nor `response` is set.
If `done == false` and there was a failure detected, `error` is set.
If `done == true`, exactly one of `error` or `response` is set. ||
|#

## CreateTargetGroupMetadata {#yandex.cloud.loadbalancer.v1.CreateTargetGroupMetadata}

#|
||Field | Description ||
|| target_group_id | **string**

ID of the target group that is being created. ||
|#

## TargetGroup {#yandex.cloud.loadbalancer.v1.TargetGroup}

A TargetGroup resource. For more information, see [Target groups and resources](/docs/network-load-balancer/concepts/target-resources).

#|
||Field | Description ||
|| id | **string**

Output only. ID of the target group. ||
|| folder_id | **string**

ID of the folder that the target group belongs to. ||
|| created_at | **[google.protobuf.Timestamp](https://developers.google.com/protocol-buffers/docs/reference/google.protobuf#timestamp)**

Output only. Creation timestamp in [RFC3339](https://www.ietf.org/rfc/rfc3339.txt) text format. ||
|| name | **string**

Name of the target group.
The name is unique within the folder. 3-63 characters long. ||
|| description | **string**

Description of the target group. 0-256 characters long. ||
|| labels | **string**

Resource labels as `` key:value `` pairs. Maximum of 64 per resource. ||
|| region_id | **string**

ID of the region where the target group resides. ||
|| targets[] | **[Target](#yandex.cloud.loadbalancer.v1.Target2)**

A list of targets in the target group. ||
|#

## Target {#yandex.cloud.loadbalancer.v1.Target2}

A Target resource. For more information, see [Target groups and resources](/docs/network-load-balancer/concepts/target-resources).

#|
||Field | Description ||
|| subnet_id | **string**

ID of the subnet that targets are connected to.
All targets in the target group must be connected to the same subnet within a single availability zone. ||
|| address | **string**

IP address of the target. ||
|#