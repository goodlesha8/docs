# Switching the master

In a failover {{ mrd-name }} cluster with multiple hosts, you can switch the master role from the current master host to the replica host. After this operation, the current master host becomes the replica host of the new master.

It takes several minutes on average to switch, and the cluster is available during that time.

A [sharded cluster](../concepts/sharding.md) contains one or more master hosts: one per [shard](../concepts/sharding.md#redis-cluster-structure). Switching the master for a sharded cluster is done for each shard one by one.

{% list tabs group=instructions %}

- Management console {#console}

    To switch the master in a non-sharded cluster:

    1. In the [management console]({{ link-console-main }}), go to the folder containing the non-sharded cluster.
    1. Select **{{ ui-key.yacloud.iam.folder.dashboard.label_managed-redis }}**.
    1. Click the name of the cluster you need and select the **{{ ui-key.yacloud.mdb.cluster.hosts.label_title }}** tab.
    1. Next to the host with the `MASTER` role, click ![image](../../_assets/console-icons/ellipsis.svg) and select **{{ ui-key.yacloud.mdb.dialogs.popup-confirm-switch-master_label-title }}**.
    1. In the window that opens, select the **{{ ui-key.yacloud.mdb.dialogs.popup-confirm-switch-master_label_confirmation }}** option and click **{{ ui-key.yacloud.mdb.dialogs.popup-confirm-switch-master_button }}**.

    To switch the master in a sharded cluster:

    1. In the [management console]({{ link-console-main }}), go to the folder containing the sharded cluster.
    1. Select **{{ ui-key.yacloud.iam.folder.dashboard.label_managed-redis }}**.
    1. Click the name of the cluster you need and select the **{{ ui-key.yacloud.mdb.cluster.hosts.label_title }}** tab.
    1. Next to the host with the `MASTER` role, click ![image](../../_assets/console-icons/ellipsis.svg) and select **{{ ui-key.yacloud.mdb.dialogs.popup-confirm-switch-master_label-title }}**.
    1. In the window that opens, click **{{ ui-key.yacloud.mdb.dialogs.popup-confirm-switch-master_button }}**.

- CLI {#cli}

    {% include [cli-install](../../_includes/cli-install.md) %}

    {% include [default-catalogue](../../_includes/default-catalogue.md) %}

    To switch the master in a non-sharded cluster, run the command:

    ```bash
    {{ yc-mdb-rd }} cluster start-failover \
      --name <cluster_name>
    ```

    To switch the master in a sharded cluster, run the command:

    ```bash
    {{ yc-mdb-rd }} cluster start-failover \
      --name <cluster_name> \
      --hostnames <current_master_name>
    ```

    You can request the cluster name with a [list of clusters in the folder](cluster-list.md) and the name of the master host for the desired shard with a [list of hosts in the cluster](hosts.md#list).

- API {#api}

    To switch the master, use the [startFailover](../api-ref/Cluster/startFailover.md) REST API method for the [Cluster](../api-ref/Cluster/index.md) resource or the [ClusterService/StartFailover](../api-ref/grpc/Cluster/startFailover.md) gRPC API call and provide the following in the request:

    * ID of the cluster where you want to switch the master in the `clusterId` parameter. To find out the cluster ID, get [a list of clusters in the folder](cluster-list.md).
    * For a sharded cluster only: the name of the shard's current master in the `hostNames` parameter. To find out the name, get a [list of hosts in the cluster](hosts.md#list).

{% endlist %}
