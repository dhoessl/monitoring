# Grafana Monitoring Server

This ansible role is creating a clean grafana installation on the latest opensource image.

It also provides a Influxdb as database and and creates an imagerender container for displaying images on alerts.

# Variables
in `defaults/main.yaml` there are some variables already set as a default.

Some Variables need to be set before running this role.

It is '''recommended''' to also change the usernames of the grafana and infludb user.

## Default vars
```
monitoring_state: 'present'
monitoring_proto: 'http'
monitoring_grafana_port: '3000'
monitoring_influxdb_port: '8086'
monitoring_admin_username: 'admin'
monitoring_db_username: 'admin'
monitoring_db_org: 'default'
monitoring_db_bucket: 'default'
monitoring_db_retention: '2w'
monitoring_docker_host_dir: '/var/lib/grafana'
```

## Vars which need to be set in a variable file

```
monitoring_domain:  # The Domain on which you access grafana and influxdb
monitoring_admin_password:  # Password to the grafana admin user
monitoring_db_password:  # Password to the influxdb user
```

# Future Features
* add mysql database on creation
* enable/disable image renderer and database using variables
