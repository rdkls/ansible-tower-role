# Ansible Tower

This role installs Ansible Tower.

Forked from https://github.com/kovarus/ansible-tower-role

# Requirements

A license is needed prior to using. License data can then either be put in a file (and path specified in 'license_file_path' parameter) - or passed in as a dict in the 'license_data' parameter.

For the test.yml file to be used, a license.json file needs to be placed in the tests directory.

# Role Variables

`license_file_path`
- default: blank
- description: This is a mandatory variable that specifies the path to the license file to be uploaded to Tower after installation.

`license_data`
- default: blank
- description: License data

Example:
```
tower_config:
  host: localhost
  tower_user: admin
  tower_password: password
  license_data:
    company_name: Wiley Enterprises
    hostname: 02527052e98a69b71706cf5adc872c5e
    instance_count: 500
    license_date: 43985743798
    license_key: dab38cc13e371a4b4e34b2f5cd8755c767cf8cf3864d639d28f868083982f6f1
    license_type: Enterprise
    subscription_name: Red Hat Ansible Tower, Premium (500 Managed Nodes)
    eula_accepted: 1
```

Note even though 'eula_accepted' is not stricly part of the license, it's needed in the POST 

`tower_version`
- default: 3.2.6
- description: This specifies the version of tower to be installed.

`admin_password`
- default: "password"
- description: This specifies the administrator password for Tower

`redis_password`
- default: "password"
- description: This specifies the password for the Redis cache

`postgres_username`
- default: "awx"
- description: Username for the PostgreSQL database

`postgres_password`
- default: "password"
- description: This specifies the password for the PostgreSQL database


`postgres_host`
- default: ""
- description: Host for the PostgreSQL database

`postgres_port`
- default: ""
- description: Port for the PostgreSQL database

`postgres_database`
- default: "awx"
- description: Name for the PostgreSQL database

`rabbitmq_password`
- default: "password"
- description: This specifies the password for RabbitMQ

`install_cli`
- default: True
- description: This specifies whether or not to install and configure the ansible-tower-cli pip package.

Dependencies
------------

None

Example Playbook
----------------

```json
---
- name: tower
  hosts: localhost
  roles:
    - role: tower
      license_file_path: license.json
```
License
-------

MIT

Author Information
------------------

Taylor Owen (towen@kovarus.com)
