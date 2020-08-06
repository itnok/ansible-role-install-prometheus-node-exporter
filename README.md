install-prometheus-node-exporter
================================

[![Build Status](https://travis-ci.org/itnok/ansible-role-install-prometheus-node-exporter.svg?branch=master)](https://travis-ci.org/itnok/ansible-role-install-prometheus-node-exporter) [![GitHub tag](https://img.shields.io/github/v/tag/itnok/ansible-role-install-prometheus-node-exporter?sort=semver)](https://github.com/itnok/ansible-role-install-prometheus-node-exporter/tags/) [![Ansible Role](https://img.shields.io/ansible/role/XXXXXX)](https://galaxy.ansible.com/itnok/install_prometheus_node_exporter)

Install Prometheus Node Exporter on a supported host.

Steps performed are:

  - Find latest Prometheus Node Exporter release available _(or the specified one)_
  - Check latest release available of Prometheus Node Exporter
  - Download list of SHA256 checksums for the specified release of Prometheus Node Exporter"
  - Download the specified release of Prometheus Node Exporter"
  - Create a dedicated system user for Prometheus Node Exporter _(if not already present)_"
  - Extract 'node_exporter' from {{ install_prometheus_node_exporter.name }}"
  - Set the systemd service file up for Prometheus Node Exporter"
  - Force systemd to reread configuration files for services"
  - Enable and restart systemd service for Prometheus Node Exporter"


## :exclamation: Requirements
-----------------------------

None.


## :abcd: Role Variables
------------------------

| Variable                        | Description                                         | Default Value       |
|---------------------------------|-----------------------------------------------------|---------------------|
| `install_prometheus`            | Version of Prometheus Node Exporter to install      | `latest`            |


## :link: Dependencies
----------------------

- [itnok.manage_pkg_ubuntu](https://galaxy.ansible.com/itnok/manage_pkg_ubuntu) _(:octocat: [ansible-role-manage-pkg-ubuntu](https://github.com/itnok/ansible-role-manage-pkg-ubuntu))_

To install dependencies use:
```
    $ ansible-galaxy install <dependecy.name>
```

Installation of the required Ansible Roles can also be simply addressed with:
```
    $ ansible-galaxy install -r requirements.yml
```


## :notebook: Example Playbook
------------------------------

Here an example of how to use this role in your playbooks:

```
---
- hosts: servers
  remote_user: ubuntu   # optional (your remote user)
  gather_facts: yes     # optional
  become: yes

  roles:
    - { role: itnok.install_prometheus_node_exporter }

  vars:
    install_prometheus: "latest"
```

## :guardsman: License
----------------------

MIT _([read more](LICENSE.md))_
