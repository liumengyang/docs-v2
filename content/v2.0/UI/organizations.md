---
title: Managing organizations
description: Describes how to manage organizations.
menu:
  v2_0:
    name: Managing organizations
    weight: 1
---

Everything is scoped by/contained within organization--dashboards, tasks, buckets, users, !!collectors and scrapers!!.

**To create an organization**:

1. Click the **Organizations** tab in the navigation bar.
2. Click **+ Create Organization**
2. Enter a name for your organization.
3. Click **Create**.

**To manage an organization's members**:

Organizations have "owners" and "members".

1. Click the **Organizations** tab in the navigation bar.
2. Click on the name of an organization. All of the organization's members appear in the **Members** tab.
3. Select a member from the list or search to filter the list.
4. ?? Edit members, remove members, invite users to be a member


**To manage an organization's buckets**:

A bucket is a named location where data is stored that has a retention policy. It’s similar to an InfluxDB v1.x “database,” but is a combination of both a database and a retention policy. Each bucket can only have one retention policy.


1. Click the **Organizations** tab in the navigation bar.
2. Click on the name of an organization, then select the **Buckets** tab. All of the organization's buckets appear.
3. To create a bucket, click **+Create** in the upper right.
  * Enter a name for your bucket in the **Name** field.
  * In the **How often to clear data?** field:
    * Select **Never** to retain data forever.
    * Select **Periodically** to define a specific retention policy.
4. To update a bucket's name or retention policy, click the name of the bucket from the list.
5. Click **Update** to save.
6. ??Configure data sources tied to each bucket, delete bucket


**To view an organization's dashboards**:

1. Click the **Organizations** tab in the navigation bar.
2. Click on the name of an organization, then select the **Dashboards** tab. All of the organization's dashboards appear.
3. Click on the name of the dashboard to view it.

For details on editing dashboards, see <<link to dashboards section>>


#### Tasks (/organizations/orgnamehere/tasks)
  * User can see all tasks owned by this org

#### Options (/organizations/orgnamehere/options) mockup says settings
  * Only owners can see this tab
  * Owner can change name of Organization
  * Owner can modify permissions of an organization
  * There will be more options here in the future
  * Owner can disband organization