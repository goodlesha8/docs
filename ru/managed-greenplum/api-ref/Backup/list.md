---
editable: false
sourcePath: en/_api-ref/mdb/greenplum/v1/api-ref/Backup/list.md
---

# Managed Service for Greenplum® API, REST: Backup.List

Returns the list of available backups for the specified Greenplum® cluster.

## HTTP request

```
GET https://{{ api-host-mdb }}/managed-greenplum/v1/backups
```

## Query parameters {#yandex.cloud.mdb.greenplum.v1.ListBackupsRequest}

#|
||Field | Description ||
|| folderId | **string**

Required field. ID of the folder to list backups in. ||
|| pageSize | **string** (int64)

The maximum number of results per page to return.

If the number of available results is larger than `pageSize`, the service returns a [ListBackupsResponse.nextPageToken](#yandex.cloud.mdb.greenplum.v1.ListBackupsResponse) that can be used to get the next page of results in subsequent list requests.

Default value is 100. ||
|| pageToken | **string**

The page token. To get the next page of results, set `pageToken` to the [ListBackupsResponse.nextPageToken](#yandex.cloud.mdb.greenplum.v1.ListBackupsResponse) returned by the previous list request. ||
|#

## Response {#yandex.cloud.mdb.greenplum.v1.ListBackupsResponse}

**HTTP Code: 200 - OK**

```json
{
  "backups": [
    {
      "id": "string",
      "folderId": "string",
      "createdAt": "string",
      "sourceClusterId": "string",
      "startedAt": "string",
      "size": "string",
      "type": "string",
      "method": "string",
      "journalSize": "string"
    }
  ],
  "nextPageToken": "string"
}
```

#|
||Field | Description ||
|| backups[] | **[Backup](#yandex.cloud.mdb.greenplum.v1.Backup)**

Requested list of backups. ||
|| nextPageToken | **string**

This token allows you to get the next page of results for a list request.

If the number of results is larger than [ListBackupsRequest.pageSize](#yandex.cloud.mdb.greenplum.v1.ListBackupsRequest) specified in the request, use the `nextPageToken` as the value for the [ListBackupsRequest.pageToken](#yandex.cloud.mdb.greenplum.v1.ListBackupsRequest) parameter in the next list request.

Each subsequent ListBackups request has its own `nextPageToken` to continue paging through the results. ||
|#

## Backup {#yandex.cloud.mdb.greenplum.v1.Backup}

#|
||Field | Description ||
|| id | **string**

Required. ID of the backup. ||
|| folderId | **string**

ID of the folder that the backup belongs to. ||
|| createdAt | **string** (date-time)

Time when the backup operation was completed.

String in [RFC3339](https://www.ietf.org/rfc/rfc3339.txt) text format. The range of possible values is from
`0001-01-01T00:00:00Z` to `9999-12-31T23:59:59.999999999Z`, i.e. from 0 to 9 digits for fractions of a second.

To work with values in this field, use the APIs described in the
[Protocol Buffers reference](https://developers.google.com/protocol-buffers/docs/reference/overview).
In some languages, built-in datetime utilities do not support nanosecond precision (9 digits). ||
|| sourceClusterId | **string**

ID of the Greenplum® cluster that the backup was created for. ||
|| startedAt | **string** (date-time)

Time when the backup operation was started.

String in [RFC3339](https://www.ietf.org/rfc/rfc3339.txt) text format. The range of possible values is from
`0001-01-01T00:00:00Z` to `9999-12-31T23:59:59.999999999Z`, i.e. from 0 to 9 digits for fractions of a second.

To work with values in this field, use the APIs described in the
[Protocol Buffers reference](https://developers.google.com/protocol-buffers/docs/reference/overview).
In some languages, built-in datetime utilities do not support nanosecond precision (9 digits). ||
|| size | **string** (int64)

Size of the backup in bytes. ||
|| type | **enum** (BackupCreationType)

How this backup was created (manual/automatic/etc...)

- `BACKUP_CREATION_TYPE_UNSPECIFIED`
- `AUTOMATED`: Backup created by automated daily schedule
- `MANUAL`: Backup created by user request ||
|| method | **enum** (BackupMethod)

Method of backup creation

- `BACKUP_METHOD_UNSPECIFIED`
- `BASE`: Base backup
- `INCREMENTAL`: Delta (incremental) Greenplum backup ||
|| journalSize | **string** (int64)

Size of the journal associated with backup, in bytes ||
|#