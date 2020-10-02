
# Metrics Exporter

#### Easy Install with PM2

```shell
pm2 install @saulx/metrics-exporter
```

#### Or Clone and run as a seperate application

```shell
    $ git clone https://github.com/saikatharryc/pm2-prometheus-exporter.git
    $ npm install
    $ pm2 start exporter.js --name metrics-exporter
```

#### Open your browser

```shell
http://<HOST>:9209/metrics
```

#### For Prometheus Config

in `prometheus.yaml`
inside `scrape_configs` add this block:

```yml
- job_name: pm2-metrics
scrape_interval: 10s
scrape_timeout: 10s
metrics_path: /metrics
scheme: http
static_configs:
  - targets:
      - localhost:9209
```

##### Based from (PM2 Metrics)[https://github.com/saikatharryc/pm2-prometheus-exporter].
