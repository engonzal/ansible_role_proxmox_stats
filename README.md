### Ansible Roles: proxmox_stats
Role to add the InfluxDB metrics configurations for Proxmox virtualization.  More info on Proxmox stats available [here](https://pve.proxmox.com/wiki/External_Metric_Server).
[![Build Status](https://travis-ci.org/engonzal/ansible_role_proxmox_stats.svg?branch=master)](https://travis-ci.org/engonzal/ansible_role_proxmox_stats)

#### Role Variables
Setting the InfluxDB servername and port is supported.  Note that the UDP input is required to be configured on your InfluxDB server.  note below "influx" should be "your-influx-database-hostname"
```
proxmox_stats_influx_server: influx
proxmox_stats_influx_port: "8089"
```

#### Example Playbook

```
    - hosts: servers
      vars:
        proxmox_stats_influx_server: influx.engonzal.com
        proxmox_stats_influx_port: "8089"
      roles:
         - { role: engonzal.proxmox_stats, tags: [ 'proxmox_stats'] }
```

#### Todo
 * Add support for graphite.
 * Add instructions to configure InfluxDB UDP configs

#### License

BSD
