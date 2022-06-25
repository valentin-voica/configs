# Configuration Files
Configuration files for my networked devices

## Configure a static IP address on Ubuntu Server 20.04 LTS

**NETPLAN** is the default network management tool on systems running Ubuntu 17.10 and newer. The configuration files for Netplan are written in YAML.

'systemd-networkd' is the default renderer for servers (systems with no GUI).

The `50-cloud-init.yaml` in this repo has the configuration for my system and network:

* interface `eth0`
* subnet in "Servers" VLAN:
  - network: 172.20.30.0 /28
  - IP address: 172.20.30.3
  - gateway: 172.20.30.1
  - DNS server: 172.20.30.2

My Ubuntu instance is not provisioned with `cloud-init`, so there is no need to disable it (no need to create the `/etc/cloud/cloud.cfg.d/99-disable-network-config.cfg` file with the content `network: {config: disabled}`
