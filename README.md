# Домашнее задание к занятию 10.03. Grafana

# Задание 1

  ![Скриншот datasource](https://github.com/chuckberry321/netology-10-monitoring-03-grafana/blob/main/pictures/grafana_data_source.png)

# Задание 2

  - Утилизация CPU для nodeexporter (в процентах, 100-idle):
```
100 - (avg by (instance) (rate(node_cpu_seconds_total{job="nodeexporter",mode="idle"}[1m])) * 100)
```

  - CPULA 1/5/15:
```
node_load1{instance="nodeexporter:9100", job="nodeexporter"}
node_load5{instance="nodeexporter:9100", job="nodeexporter"}
node_load15{instance="nodeexporter:9100", job="nodeexporter"}
```

  - Количество свободной оперативной памяти:
```
avg_over_time (node_memory_MemFree_bytes{instance="nodeexporter:9100", job="nodeexporter"}[10s])
```

  - Количество места на файловой системе:
```
node_filesystem_avail_bytes {instance="nodeexporter:9100", job="nodeexporter", mountpoint="/"}
```

  ![Скриншот dashboard](https://github.com/chuckberry321/netology-10-monitoring-03-grafana/blob/main/pictures/grafana_dashboard_1.png)

# Задание 3

  ![Скриншот dashboard](https://github.com/chuckberry321/netology-10-monitoring-03-grafana/blob/main/pictures/grafana_dashboard_2.png)

# Задание 4

  ![Dashboard JSON](https://github.com/chuckberry321/netology-10-monitoring-03-grafana/blob/main/grafana_dashboard.json)
