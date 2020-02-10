# Grafana Dashboard for Curity Identity Server

Curity Identity Server publishes prometheus-compliant metrics. Grafana is a tool that can be used to visualize the metrics collected by Prometheus.
This repository provides a preconfigured dashboard that shows the most important metrics of Curity Identity Server. Feel free to download the .json file and import it into your Grafana instance to view all the stats of your Curity Identity Server instance.

# Prerequisites

To use this dashboard, you must have an environment that has at least the following systems installed:

* An instances of Curity Identity Server with metrics enabled (enabled by default and listening on port 4466)
* An instance of Prometheus that polls the metrics from Curity Identity Server.
Check out [Getting Started with Prometheus](https://prometheus.io/docs/prometheus/latest/getting_started/)
* An instance of Grafana with a datasource configured that points to the Prometheus instance above:
Check out [Getting Started with Grafana](https://grafana.com/docs/grafana/latest/guides/getting_started/)

# Quickstart Guide
If you just want to review the dashboard, consider to setup your environment using Docker. For that purpose a configuration file for Prometheus and a docker-compose file were added to the repository. Using docker-compose you can start the required containers with a single command.
Run the following command inside the repository to create an environment:

```
docker-compose up
```

This will setup three containers with the necessary ports forwarded for each system:
* idsvr
* prometheus
* grafana

The same names can be used in configuration files to refer to the applications and Docker deamon will handle the name resolution and routing.

| Endpoint                       | Description                                                  |
|--------------------------------|--------------------------------------------------------------|
| https://localhost:6749/admin   | Admin UI for Curity Identity Server
| http://localhost:4466/metrics  | Raw metrics published by Curity Identity Server              |
| http://localhost:9090/targets  | Endpoint to check status of targets configured in Prometheus |
| http://localhost:3000          | Grafana Web UI                                               |


1. Access Grafana through the web interface: http://localhost:3000
1. Create a new datasource of type Prometheus.
1. Enter the URL for your Prometheus instance (backend): http://prometheus:9090
1. Test and save the configuration.
1. Add this dashboard by importing the .json file in this repository.
  1. On the left menu hover the dashboard icon and select manage (http://localhost:3000/dashboards).
  1. Click on import.
  1. Upload the .json file.
1. Congratulations, you are ready to explore the dashboard for Curity Identity Server.

# Contributing

Pull requests are welcome. To do so, just fork this repo, and submit a pull request.

# License

The files and resources maintained in this repository are licensed under the [Apache 2 license](LICENSE).

# More Information

Please visit [curity.io](https://curity.io/) for more information about the Curity Identity Server.

Copyright (C) 2020 Curity AB.
