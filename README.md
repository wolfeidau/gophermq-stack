gophermq-stack
=========

Ties together influxdb, letsencrypt, mosquiotto and grafana using Ansible and Docker.

This stack was demonstrated as a part of my talk at hardware miniconf, linuxconfau 2016.

It is provided to illustrate how a stack for IoT time series can be built using OPS tools.

Requirements
------------

* Docker
* Ubuntu

Role Variables
--------------

```
# root password
influxdb_pass: xxx
# admin user password
grafana_pass: xxx
# used to authenticate against github
github_client_id: xxx
github_client_secret: xxx
# These MUST be registered in DNS before being used if you want to use
# letsencrypt.
influxdb_hostname: iot.example.com
mosquitto_hostname: mqtt.example.com
grafana_hostname: graphs.example.com
letsencrypt_recovery_email: me@example.com
```

Dependencies
------------

* franklinkim.docker
* franklinkim.docker-compose

Example Playbook
----------------

Including an example of how to use your role (for instance, with variables passed in as parameters) is always nice for users too:

```
- hosts: iotservers
  remote_user: root
  roles:
    - wolfeidau.gophermq-stack
    - franklinkim.docker
    - franklinkim.docker-compose
  vars:
    docker_compose_version: 1.5.1
    influxdb_pass: xxx
    grafana_pass: xxx
    github_client_id: xxx
    github_client_secret: xxx
    influxdb_hostname: iot.example.com
    mosquitto_hostname: mqtt.example.com
    grafana_hostname: graphs.example.com
    letsencrypt_recovery_email: me@example.com
```

License
-------

BSD

Author Information
------------------

Copyright (c) 2014 Mark Wolfe Licensed under the BSD license.
