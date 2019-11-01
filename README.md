monitoring stack
=========

Helper role for https://github.com/hatifnatt/monitoring_stack

Requirements
------------

- git
- Ansible (2.8+ recommended)
- docker
- docker-compose

Example Playbook
----------------

```
- hosts: servers
  vars:
    # email for notifications from Let's Encrypt
    default_email: my@email.tld
    postgres_password: postgres
    zabbix_dbpassword: zabbix
    zabbix_ro_dbpassword: grafana
    # Recommended to create a user with read only access to all hosts in Zabbix
    # By defaul super administrator 'Admin' is used
    zabbix_api_user: Admin
    zabbix_api_password: zabbix
    # Grafna admin password
    grafana_password: grafana
    # Vhost for Zabbix, Grafana and Prometheus, if not set or set to empty string proxying will be disabled
    # default is empty string
    zabbix_vhost: ''
    prom_vhost: ''
    grafana_vhost: ''
  roles:
      - monitoring_stack
```
