[[Grafana]] [[Odoo]]

`Loki Config for docker`
```yaml
auth_enabled: false
server:
	http_listen_port: 3100
	grpc_listen_port: 9096
common:
	instance_addr: 127.0.0.1
	path_prefix: /tmp/loki	
	storage:
		filesystem:
		chunks_directory: /tmp/loki/chunks
		rules_directory: /tmp/loki/rules
	replication_factor: 1
	ring:
		kvstore:
			store: inmemory
query_range:
    results_cache:
      cache:
        embedded_cache:
          enabled: true
          max_size_mb: 100
schema_config:
    configs:
      - from: 2020-10-24
        store: boltdb-shipper
        object_store: filesystem
        schema: v11
        index:
          prefix: index_
          period: 24h
ruler:
    alertmanager_url: http://localhost:9093
```

`Promptail Config for Docker`
```yaml
server:
  http_listen_port: 9080
  grpc_listen_port: 0
positions:
  filename: /tmp/positions.yaml
clients:
  - url: http://loki:3100/loki/api/v1/push
scrape_configs:
- job_name: odoolog
  static_configs:
  - targets:
      - localhost
    labels:
      job: odoolog
      __path__: /var/log/odoo/*log
```

```yml
version: "3"
networks:
  loki:
services:
  loki:
    container_name: loki
    image: grafana/loki:2.8.0
    volumes:
      - ./config:/mnt/config/
    ports:
      - "3100:3100"
    command: -config.file=/mnt/config/loki-local-config.yaml
    networks:
      - loki

  promtail:
    container_name: promtail
    image: grafana/promtail:2.8.0
    volumes:
      - ./config:/mnt/config/
      - /var/log/odoo:/var/log/odoo/
    command: -config.file=/mnt/config/promtail-config.yaml
    networks:
      - loki

  grafana:
    environment:
      - GF_PATHS_PROVISIONING=/etc/grafana/provisioning
      - GF_AUTH_ANONYMOUS_ENABLED=true
      - GF_AUTH_ANONYMOUS_ORG_ROLE=Admin
    entrypoint:
      - sh
      - -euc
      - |
        mkdir -p /etc/grafana/provisioning/datasources
        cat <<EOF > /etc/grafana/provisioning/datasources/ds.yaml
        apiVersion: 1
        datasources:
        - name: Loki
          type: loki
          access: proxy 
          orgId: 1
          url: http://192.168.1.14:3100
          basicAuth: false
          isDefault: true
          version: 1
          editable: false
        EOF
        /run.sh
    container_name: grafana
    image: grafana/grafana:latest
    ports:
      - "3000:3000"
    networks:
      - loki
```

```bash
wget https://raw.githubusercontent.com/grafana/loki/v2.8.0/cmd/loki/loki-local-config.yaml  \ 
-O loki-config.yaml
wget https://raw.githubusercontent.com/grafana/loki/v2.8.0/clients/cmd/promtail/promtail-docker-config.yaml   \
-O promtail-config.yaml
```

