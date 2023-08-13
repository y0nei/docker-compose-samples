# Prometheus + Grafana

A docker-compose template for [Prometheus] metrics, [Grafana] dashboard, 
[Cadvisor] container monitor and [Node-exporter]

## Stack
- **Prometheus**: Used to expose various metrics & manage data sources.
- **Grafana** `OSS`: Operational dashboards to view your data, alerts, various
plugins and more.
- **Cadvisor**: Collects, aggregates, processes, and exports information about
running containers.
- **Node exporter**: Hardware and OS metrics

## Table of contents
- [.env](.env): Used for storing grafana admin credentials
- [prometheus.yml](prometheus.yml): Prometheus config with pre-configured scraping jobs
- [grafana/datasource.yml](grafana/datasource.yml): Pre-configured prometheus data source for grafana
*(no need to set that manually in the dashboard)*

## Deploying
Just run `docker compose up -d` to run the stack in the background, and then
access grafana via `http://localhost:6010`  
To view logs run `docker compose logs -f` and to stop the container
`docker compose down`

To test out the newly running monitoring stack, here are some cool dashboards
i use:
- **For Cadvisor**: ID: `14282`, [Dashboard source][1]
- **For Node exporter**: ID: `1860`, [Dashboard source][2]

## Note
This was tested on a RPI 4b+, previously to get ARMv7 support it was required to
run [ZCube/cadvisor-docker](https://github.com/ZCube/cadvisor-docker) but now
the regular ghcr.io image works fine without additional configuration or
specifying an architecture. If you still face issues with other architectures,
please refer to the [Cadvisor] readme, it has valuable information.  
Grafana also previously had some issues with permissions and persistent storage
but all now is fixed which is phenomenal!

[1]: https://grafana.com/grafana/dashboards/14282-cadvisor-exporter/
[2]: https://grafana.com/grafana/dashboards/1860-node-exporter-full/

[Prometheus]: https://prometheus.io/
[Grafana]: https://grafana.com/
[Cadvisor]: https://github.com/google/cadvisor
[Node-exporter]: https://github.com/prometheus/node_exporter
