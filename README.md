# ansible-ovirt_exporter

Role for deploy Prometheus
[ovirt_exporter](https://github.com/czerwonk/ovirt_exporter)

## Requirements

* Ansible 3.0.0+;

Example configuration
-------------------------

```yaml
ovirt_exporter:
  # version of the exporter:
  # bare value, like '1.5.2'
  # 'latest' - the latest release from Github
  - version: 'latest'
    # enable exporter service or not
    enable: 'true'
    # restart exporter service or not
    restart: 'true'
    # The configuration of ovirt_exporter
    settings:
      - debug: 'true'
        url: 'https://localhost/ovirt-engine/api/'
        username: 'admin@internal'
        password: 'secret'
        insecure: 'false'
        with_snapshots: 'false'
        with_network: 'false'
        with_disks: 'false'
        listen_address: ':9325'
        telemetry_path: '/metrics'
```
