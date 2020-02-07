# Grafana Dashboard for Curity Identity Server

Curity Identity Server publishes prometheus-compliant metrics. Grafana is a tool that can be used to visualize the metrics collected by Prometheus.
This repository provides a preconfigured Dashboard that shows the most important metrics of Curity Identity Server. Feel free to download the .json file and import it into your Grafana instance to view all the stats of your Curity Identity Server instance.

# Prerequisites

In order to be able to use this Dashboard you must have an environment that has at least the following systems installed:

* An instances of Curity Identity Server with metrics enabled (default on and listening on port 4466)
* An instance of Prometheus that polls the metrics from Curity Identity Server.
Check out [Getting Started with Prometheus](https://prometheus.io/docs/prometheus/latest/getting_started/)
* An instance of Grafana with a datasource configured that points to the Prometheus instance above:
Check out [Getting Started with Grafana](https://grafana.com/docs/grafana/latest/guides/getting_started/)

# Quickstart Guide
If you just want to review the Dashboard, consider to setup your environment using Docker. For that purpose a configuration file for Prometheus was added to the repository.

```
docker run -d -p 6749:6749 -p 4466:4466 curity/idsvr
docker run -d -p 9090:9090 -v /fullpath/to/prometheus.yml:/etc/prometheus/prometheus.yml prom/prometheus
docker run -d -p 3000:3000 grafana/grafana
```


| Endpoint                       | Description                                                  |
|--------------------------------|--------------------------------------------------------------|
| https://localhost:6749/admin   | Admin UI for Curity Identity Server
| http://localhost:4466/metrics  | Raw metrics published by Curity Identity Server              |
| http://localhost:9090/targets  | Endpoint to check status of targets configured in Prometheus |
| http://localhost:3000          | Grafana Web UI                                               |


* Access Grafana through the web interface: http://localhost:3000
* Create a new datasource of type Prometheus.
* Enter the URL for your Prometheus instance: http://localhost:9090
* Test and save the configuration.
* Add a new Dashboard by importing the .json file in this repository.

# Contributing

Pull requests are welcome. To do so, just fork this repo, and submit a pull request.

# License

The files and resources maintained in this respository are licensed under the [Apache 2 license](LICENSE).

# More Information

Please visit [curity.io](https://curity.io/) for more information about the Curity Identity Server.

Copyright (C) 2019 Curity AB.
