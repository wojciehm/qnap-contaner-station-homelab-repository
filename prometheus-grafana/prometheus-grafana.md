# Prometheus with Grafana deployment.

## Prometheus
First we provide [Prometheus](docker-compose.yaml) docker compose file.

I use configuration file located in [prometheus.yaml](prometheus-provisioning/prometheus.yml).

Part of the code is used to provide config for prometheus 

```
command:
      - --config.file=/etc/prometheus/prometheus.yml
    volumes:
      - ./prometheus-provisioning/prometheus.yml:/etc/prometheus/prometheus.yml
```
## Grafana
Similar to Prometheus we use Grafana configuration files located in grafana-provisioning directory. First one is for [dashboard](grafana-provisioning/dashboards/default.yaml) and second [configuration file](grafana-provisioning/datasources/default.yaml) is for datasources.  

```
volumes:
      - ./grafana-provisioning/dashboards:/etc/grafana/provisioning/dashboards
      - ./grafana-provisioning/datasources:/etc/grafana/provisioning/datasources
      - monitoring_grafana_data:/var/lib/grafana # Volume for Grafana data
```