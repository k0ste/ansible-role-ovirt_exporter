# ansible-ovirt_exporter

Role for deploy Prometheus
[ovirt_exporter](https://github.com/czerwonk/ovirt_exporter)

## Requirements

* Ansible 3.0.0+

Example configuration
-------------------------

```yaml
ovirt_exporter:
  # Install/upgrade exporter package, otherwise binary from Github will
  # be installed
  - install_package: 'true'
  # 'present' (do nothing if package is already installed) or 'latest' (always
  # upgrade to last version)
    package_state: 'latest'
  # version of the exporter in case of Github deployment (not relevant for
  # package deployment): bare value, like '0.8.0' or latest' - the latest
  # release from Github
    version: 'latest'
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
