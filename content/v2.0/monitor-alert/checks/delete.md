---
title: Delete checks
seotitle: Delete monitoring checks in InfluxDB
description: >
  Delete checks in the InfluxDB UI.
menu:
  v2_0:
    parent: Manage checks
weight: 204
related:
  - /v2.0/monitor-alert/notification-rules/
  - /v2.0/monitor-alert/notification-endpoints/
---

If you no longer need a check, use the InfluxDB user interface (UI) to delete it.

{{% warn %}}
Deleting a check cannot be undone.
{{% /warn %}}

1.  Click **Monitoring & Alerting** in the sidebar.

    {{< nav-icon "alerts" >}}

2.  In the **Checks** column, hover over the check you want to delete, click the
    **{{< icon "delete" >}}** icon, then **Delete**.

After a check is deleted, all statuses generated by the check remain in the `_monitoring`
bucket until the retention period for the bucket expires.

{{% note %}}
You can also [disable a check](/v2.0/monitor-alert/checks/update/#enable-or-disable-a-check)
without having to delete it.
{{% /note %}}