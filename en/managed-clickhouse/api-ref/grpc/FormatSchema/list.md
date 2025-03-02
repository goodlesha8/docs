---
editable: false
sourcePath: en/_api-ref-grpc/mdb/clickhouse/v1/api-ref/grpc/FormatSchema/list.md
---

# Managed Service for ClickHouse API, gRPC: FormatSchemaService.List

Returns a list of format schemas in a cluster.

## gRPC request

**rpc List ([ListFormatSchemasRequest](#yandex.cloud.mdb.clickhouse.v1.ListFormatSchemasRequest)) returns ([ListFormatSchemasResponse](#yandex.cloud.mdb.clickhouse.v1.ListFormatSchemasResponse))**

## ListFormatSchemasRequest {#yandex.cloud.mdb.clickhouse.v1.ListFormatSchemasRequest}

```json
{
  "cluster_id": "string",
  "page_size": "int64",
  "page_token": "string"
}
```

#|
||Field | Description ||
|| cluster_id | **string**

Required field. ClickHouse cluster ID.

To get a ClickHouse cluster ID, use the [ClusterService.List](/docs/managed-clickhouse/api-ref/grpc/Cluster/list#List) method. ||
|| page_size | **int64**

The maximum number of results per page to return. If the number of the results is larger than `page_size`, the service returns [ListFormatSchemasResponse.next_page_token](#yandex.cloud.mdb.clickhouse.v1.ListFormatSchemasResponse). You can use it to get the next page of the results in subsequent requests of a format schema list. ||
|| page_token | **string**

Page token. To get the next page of results, set `page_token` to the [ListFormatSchemasResponse.next_page_token](#yandex.cloud.mdb.clickhouse.v1.ListFormatSchemasResponse) returned by the previous format schema list request. ||
|#

## ListFormatSchemasResponse {#yandex.cloud.mdb.clickhouse.v1.ListFormatSchemasResponse}

```json
{
  "format_schemas": [
    {
      "name": "string",
      "cluster_id": "string",
      "type": "FormatSchemaType",
      "uri": "string"
    }
  ],
  "next_page_token": "string"
}
```

#|
||Field | Description ||
|| format_schemas[] | **[FormatSchema](#yandex.cloud.mdb.clickhouse.v1.FormatSchema)**

List of format schemas. ||
|| next_page_token | **string**

This token allows you to get the next page of results when requesting the format schema list. If the number of the results is larger than [ListFormatSchemasRequest.page_size](#yandex.cloud.mdb.clickhouse.v1.ListFormatSchemasRequest), use the `next_page_token` as the value for the [ListFormatSchemasRequest.page_token](#yandex.cloud.mdb.clickhouse.v1.ListFormatSchemasRequest) parameter in the next request. Each subsequent request will have its own `next_page_token` to continue paging through the results. ||
|#

## FormatSchema {#yandex.cloud.mdb.clickhouse.v1.FormatSchema}

#|
||Field | Description ||
|| name | **string**

Format schema name. ||
|| cluster_id | **string**

ClickHouse cluster ID. ||
|| type | enum **FormatSchemaType**

Schema type. Possible values are the following:

* FORMAT_SCHEMA_TYPE_PROTOBUF - [Protobuf](https://protobuf.dev/) data format (including [ProtobufSingle](https://clickhouse.com/docs/en/interfaces/formats#protobufsingle)).
* FORMAT_SCHEMA_TYPE_CAPNPROTO - [Cap'n Proto](https://capnproto.org/) data format.

- `FORMAT_SCHEMA_TYPE_UNSPECIFIED`
- `FORMAT_SCHEMA_TYPE_PROTOBUF`
- `FORMAT_SCHEMA_TYPE_CAPNPROTO` ||
|| uri | **string**

Link to the file of a format schema in Yandex Object Storage. Managed Service for ClickHouse works only with format schemas imported to Object Storage. ||
|#