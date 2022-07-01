# Grafana Dashboard for Curity Identity Server

[![Quality](https://img.shields.io/badge/quality-production-green)](https://curity.io/resources/code-examples/status/)
[![Availability](https://img.shields.io/badge/availability-binary-blue)](https://curity.io/resources/code-examples/status/)

Curity Identity Server publishes prometheus-compliant metrics. Grafana is a tool that can be used to visualize the metrics collected by Prometheus.
This repository provides a preconfigured dashboard that shows the most important metrics of Curity Identity Server. Feel free to download the .json file and import it into your Grafana instance to view all the stats of your Curity Identity Server instance.

# Prerequisites

To use this dashboard, you must have an environment that has at least the following systems installed:

* An instance of Curity Identity Server with metrics enabled (enabled by default and listening on port 4466)
* An instance of Prometheus that polls the metrics from Curity Identity Server.
Check out [Getting Started with Prometheus](https://prometheus.io/docs/prometheus/latest/getting_started/)
* An instance of Grafana with a datasource configured that points to the Prometheus instance above:
Check out [Getting Started with Grafana](https://grafana.com/docs/grafana/latest/guides/getting_started/)

# The Curity Identity Server Version

Since version 2.0. this dashboard is configured to work with versions of the Curity Identity Server from 7.0. onwards.
For previous versions of the Curity Identity Server use version 1.0.2 of the dashboard.

# Quickstart Guide
If you just want to review the dashboard, consider to setup your environment using Docker. For that purpose a configuration files for Prometheus and Grafana as well as a docker-compose file were added to the repository. Using docker-compose you can configure and start the required containers with a single command.
Run the following command inside the repository to create an environment:

```
docker-compose up
```

This will setup three containers with the necessary ports forwarded for each system:
* idsvr
* prometheus
* grafana

The same names are used in configuration files to refer to the applications and Docker daemon will handle the name resolution and routing.
The systems are preconfigured. Just access Grafana with the default password (see [Grafana Configuration](https://grafana.com/docs/grafana/latest/installation/configuration/#admin-user)) and select "Curity Identity Server" from the list of recent dashboards.

| Endpoint                       | Description                                                  |
|--------------------------------|--------------------------------------------------------------|
| https://localhost:6749/admin   | Admin UI for Curity Identity Server                          |
| http://localhost:4466/metrics  | Raw metrics published by Curity Identity Server              |
| http://localhost:9090/targets  | Endpoint to check status of targets configured in Prometheus |
| http://localhost:3000          | Grafana Web UI                                               |

If you have an existing installation of Curity Identity Server, Prometheus and Grafana, just add this Dashboard by importing [idsvr-dashboard.json](idsvr-dashboard.json).

## Teardown

Once you're done with evaluating the dashboard run `docker-compose rm` to remove any created containers.

# Contributing

Pull requests are welcome. To do so, just fork this repo, and submit a pull request.

# License

The files and resources maintained in this repository are licensed under the [Apache 2 license](LICENSE).

# More Information

Please visit [curity.io](https://curity.io/) for more information about the Curity Identity Server.

Copyright (C) 2020 Curity AB.
