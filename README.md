# Beehive Ansible role

[![Build Status](https://travis-ci.org/morbidick/ansible-role-beehive.svg?branch=master)](https://travis-ci.org/morbidick/ansible-role-beehive)

Installs and configures [beehive](https://github.com/muesli/beehive).

## Requirements

None. For a production environment an authentication and ssl proxy should be added.

## Example playbook

````yaml
- hosts: all
  become: yes

  roles:
  - beehive

  vars:
    beehive_canonicalurl: "http://beehive.example.net"
    beehive_bind_address: "0.0.0.0:80"
````

## Role variables

None of the variables below are required.

| Variable                 | Default   | Comment |
| :---                     | :---      | :---    |
| `beehive_canonicalurl`   | http://localhost:8181 | Canonical URL for the API & admin interface. |
| `beehive_bind_address`   | localhost:8181 | Bind address for Beehive's API & admin interface. |
| `beehive_install_go`     | `yes`     | Set to `no` if you're installing go manually or with another role. |
| `beehive_path`           | `/opt/beehive` | Where to download beehive to. |
| `beehive_config_path`    | `/etc/beehive/beehive.conf` | The beehive config file path. |
| `beehive_enable_systemd` | `yes`     | Create systemd unit file and activate. |

For all options see [defaults/main.yml](defaults/main.yml)

## Development

You can use the [Vagrantfile](Vagrantfile) for local testing, just install vagrant and virtualbox and execute the following commands:

````bash
vagrant up
vagrant provision
````

## License

MIT
