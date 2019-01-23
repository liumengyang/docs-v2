---
title: Get started with InfluxDB
description: Download, install, and setup InfluxDB, creating a default organization, user, and bucket.
menu:
  v2_0:
    name: Get started
    weight: 1
---

Get started with InfluxDB v2.0 by downloading InfluxDB, installing the necessary
executables, and running the the initial setup process.

{{< tabs-wrapper >}}
{{% tabs %}}
[macOS](#)
[Linux](#)
[Docker](#)
{{% /tabs %}}

<!-------------------------------- BEGIN macOS -------------------------------->
{{% tab-content %}}
### Download and install InfluxDB v2.0 alpha
Download InfluxDB v2.0 alpha for macOS.

<a class="btn download" href="https://dl.influxdata.com/influxdb/releases/influxdb_2.0.0-alpha.1_darwin_amd64.tar.gz" download>InfluxDB v2.0 alpha (macOS)</a>

### Place the executables in your $PATH
Unzip the download package and place the `influx` and `influxd` executables in your system `$PATH`.

```sh
# Example
cp ~/Downloads/influxdb_2.0.0-alpha.1_darwin_amd64/{influx,influxd} /usr/local/bin/
```

### Networking ports
By default, InfluxDB uses TCP port `9999` for client-server communication over InfluxDB’s HTTP API.

## Start InfluxDB
Start InfluxDB by running the `influxd` daemon:

```bash
influxd
```

_See the [`influxd` documentation](/v2.0/reference/cli/influxd) for information about
available flags and options._

{{% note %}}
#### InfluxDB "phone home"
By default, InfluxDB sends telemetry data back to InfluxData.
The [InfluxData telemetry](https://www.influxdata.com/telemetry) page provides
information about what data is collected and how it is used.

Top opt-out of sending telemetry data back to InfluxData, include the
`--reporting-disabled` flag when starting `influxd`.

```bash
influxd --reporting-disabled
```
{{% /note %}}

{{% /tab-content %}}
<!--------------------------------- END macOS --------------------------------->

<!-------------------------------- BEGIN Linux -------------------------------->
{{% tab-content %}}
### Download and install InfluxDB v2.0 alpha
Download InfluxDB v2.0 alpha package appropriate for your chipset.

<a class="btn download" href="https://dl.influxdata.com/influxdb/releases/influxdb_2.0.0-alpha.1_linux_amd64.tar.gz" download >InfluxDB v2.0 alpha (amd64)</a>
<a class="btn download" href="https://dl.influxdata.com/influxdb/releases/influxdb_2.0.0-alpha.1_linux_arm64.tar.gz" download >InfluxDB v2.0 alpha (arm)</a>

### Place the executables in your $PATH
Unzip the download package and place the `influx` and `influxd` executables in your system `$PATH`.

```sh
# Example
cp /path/to/{influx,influxd} /usr/local/bin/
```

### Networking ports
By default, InfluxDB uses TCP port `9999` for client-server communication over InfluxDB’s HTTP API.

## Start InfluxDB
Start InfluxDB by running the `influxd` daemon:

```bash
influxd
```

_See the [`influxd` documentation](/v2.0/reference/cli/influxd) for information about
available flags and options._

{{% note %}}
#### InfluxDB "phone home"
By default, InfluxDB sends telemetry data back to InfluxData.
The [InfluxData telemetry](https://www.influxdata.com/telemetry) page provides
information about what data is collected and how it is used.

Top opt-out of sending telemetry data back to InfluxData, include the
`--reporting-disabled` flag when starting `influxd`.

```bash
influxd --reporting-disabled
```
{{% /note %}}

{{% /tab-content %}}
<!--------------------------------- END Linux --------------------------------->

<!-------------------------------- BEGIN Docker ------------------------------->
{{% tab-content %}}
### Download and run InfluxDB v2.0 alpha
Use `docker run` to download and run the InfluxDB v2.0 alpha Docker image.
Expose port `9999`, which InfluxDB uses for client-server communication over its HTTP API.

```sh
docker run --name influxdb -p 9999:9999 quay.io/influxdb/influxdb:2.0.0-alpha
```

{{% note %}}
#### InfluxDB "phone home"
By default, InfluxDB sends telemetry data back to InfluxData.
The [InfluxData telemetry](https://www.influxdata.com/telemetry) page provides
information about what data is collected and how it is used.

Top opt-out of sending telemetry data back to InfluxData, include the
`--reporting-disabled` flag when starting the InfluxDB container.

```bash
docker run -p 9999:9999 quay.io/influxdb/influxdb:2.0.0-alpha --reporting-disabled
```
{{% /note %}}

### Console into the InfluxDB Container (Optional)
To use the `influx` command line interface, console into the `influxdb` Docker container:

```bash
docker exec -it influxdb /bin/bash
```

{{% /tab-content %}}
<!--------------------------------- END Docker -------------------------------->

{{< /tabs-wrapper >}}

## Setup InfluxDB
The initial setup process for InfluxDB walks through creating a default organization,
user, and bucket.
The setup process is available in both the InfluxDB user interface (UI) and in
the `influx` command line interface (CLI).

{{< tabs-wrapper >}}
{{% tabs %}}
[UI Setup](#)
[CLI Setup](#)
{{% /tabs %}}

<!------------------------------- BEGIN UI Setup ------------------------------>
{{% tab-content %}}
### Set up InfluxDB through the UI

1. With InfluxDB running, visit [localhost:9999](http://localhost:9999).
2. Click **Get Started**

#### Set up your initial user

1. Enter a **Username** for your initial user.
2. Enter a **Password** and **Confirm Password** for your user.
3. Enter your initial **Organization Name**.
4. Enter your initial **Bucket Name**.
5. Click **Continue**.

InfluxDB is now initialized with a primary user, organization, and bucket.
You are ready to [collect data](/v2.0/collect-data).

{{% /tab-content %}}
<!-------------------------------- END UI Setup ------------------------------->

<!------------------------------ BEGIN CLI Setup ------------------------------>
{{% tab-content %}}
### Set up InfluxDB through the influx CLI
Begin the InfluxDB setup process via the `influx` CLI by running:

```bash
influx setup
```

1. Enter a **primary username**.
2. Enter a **password** for your user.
3. **Confirm your password** by entering it again.
4. Enter a name for your **primary organization**.
5. Enter a name for your **primary bucket**.
6. Enter a **retention period** (in hours) for your primary bucket.
   Enter nothing for an infinite retention period.
7. Confirm the details for your primary user, organization, and bucket.

InfluxDB is now initialized with a primary user, organization, and bucket.
You are ready to [collect data](/v2.0/collect-data).

{{% /tab-content %}}
<!------------------------------- END UI Setup -------------------------------->
{{< /tabs-wrapper >}}

{{% note %}}
### Bug Reports and Feedback
Thank you for being willing to help test InfluxDB v2.0 alpha!
Feedback and bug reports are welcome and encouraged both for InfluxDB and this documentation.

[Submit feedback in the InfluxData Community](https://community.influxdata.com/c/influxdb2)
{{% /note %}}