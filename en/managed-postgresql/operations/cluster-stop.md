---
title: Stopping and starting an {{ PG }} cluster in {{ mpg-name }}
description: 'You can stop and restart a {{ PG }} DB cluster as needed. There is no charge while your cluster is idle: you continue to pay only for the storage size and backups.'
---

# Stopping and starting an {{ PG }} cluster

You can stop and restart an {{ PG }} cluster as needed. There is no charge while your cluster is idle: you continue to pay only for the storage size and backups based on the [pricing policy](../pricing.md#prices-storage).

{% include [pricing-status-warning.md](../../_includes/mdb/pricing-status-warning.md) %}

## Stopping a cluster {#stop-cluster}

{% include [cluster-stop](../../_includes/mdb/cluster-stop.md) %}

{% note info %}

A cluster that has no backups cannot be stopped. To stop it, [create its backup](../operations/cluster-backups.md#create-backup).

{% endnote %}

{% list tabs group=instructions %}

- Management console {#console}

  1. Go to the folder page and select **{{ ui-key.yacloud.iam.folder.dashboard.label_managed-postgresql }}**.
  1. Select the cluster you need in the list, click ![options](../../_assets/console-icons/ellipsis.svg), and select **{{ ui-key.yacloud.mdb.clusters.button_action-stop }}**.
  1. Confirm that you want to stop the cluster and click **{{ ui-key.yacloud.mdb.cluster.stop-dialog.popup-confirm_button }}**.

- CLI {#cli}

    {% include [cli-install](../../_includes/cli-install.md) %}

    {% include [default-catalogue](../../_includes/default-catalogue.md) %}

    To stop a cluster, run the command:

    ```bash
    {{ yc-mdb-pg }} cluster stop <cluster_name_or_ID>
    ```

    You can get the cluster ID and name with a [list of clusters in the folder](cluster-list.md#list-clusters).

- API {#api}

    To stop a cluster, use the [stop](../api-ref/Cluster/stop.md) REST API method for the [Cluster](../api-ref/Cluster/index.md) resource or the [ClusterService/Stop](../api-ref/grpc/Cluster/stop.md) gRPC API call and provide the cluster ID in the `clusterId` request parameter.

    You can get the cluster ID with a [list of clusters in the folder](cluster-list.md#list-clusters).

{% endlist %}

## Starting a cluster {#start-cluster}

You can restart **Stopped** clusters.

{% list tabs group=instructions %}

- Management console {#console}

  1. Go to the folder page and select **{{ ui-key.yacloud.iam.folder.dashboard.label_managed-postgresql }}**.
  1. Select the stopped cluster you need in the list, click ![options](../../_assets/console-icons/ellipsis.svg), and select **{{ ui-key.yacloud.mdb.clusters.button_action-start }}**.
  1. Confirm that you want to start the cluster: click **{{ ui-key.yacloud.mdb.cluster.start-dialog.popup-confirm_button }}** in the dialog box that opens.

- CLI {#cli}

    {% include [cli-install](../../_includes/cli-install.md) %}

    {% include [default-catalogue](../../_includes/default-catalogue.md) %}

    To start a stopped cluster, run the command:

    ```bash
    {{ yc-mdb-pg }} cluster start <cluster_name_or_ID>
    ```

    You can request the cluster ID and name with a [list of clusters in the folder](cluster-list.md#list-clusters).

- API {#api}

    To start a cluster, use the [start](../api-ref/Cluster/start.md) REST API method for the [Cluster](../api-ref/Cluster/index.md) resource or the [ClusterService/Start](../api-ref/grpc/Cluster/start.md) gRPC API call and provide the cluster ID in the `clusterId` request parameter.

    You can get the cluster ID with a [list of clusters in the folder](cluster-list.md#list-clusters).

{% endlist %}
