Neutron L3 agent OpenStack Ansible Role
=========

**Status**
* [![Build Status](https://travis-ci.org/openstack-ansible-galaxy/openstack-neutron_l3_agent.svg?branch=master)](https://travis-ci.org/openstack-ansible-galaxy/openstack-neutron_l3_agent) on master branch
* [![Build Status](https://travis-ci.org/openstack-ansible-galaxy/openstack-neutron_l3_agent.svg?branch=development)](https://travis-ci.org/openstack-ansible-galaxy/openstack-neutron_l3_agent) on development branch
* [![Ansible Galaxy](http://img.shields.io/badge/dguerri-openstack--neutron_l3_agent-blue.svg)](https://galaxy.ansible.com/list#/roles/1832) on Ansible Galaxy

OpenStack Neutron L3 agent installation

_Tested on Ubuntu Precise (12.04) and Trusty (14.04)_

Requirements
------------

None.

Role Variables
--------------

| Name | Default value | Description | Note |
|---   |---            |---          |---   |
| `auth_region` | `regionOne` | Authentication region (keystone) ||
| `external_interface` | `eth0` | External interface for instances network connectivity ||
| `metadata_secret` | `metadata_secret_default` | Metadata shared secret (nova) ||
| `neutron_user` | `neutron` | Neutron user as defined on Keystone ||
| `neutron_pass` | `neutron_pass_default` | Neutron service user password ||
| `neutron_tenant_name` | `service` | Neutron service tenant name ||
| `nova_metadata_ip` | `localhost` | Nova metadata server host/IP address ||
| `keystone_hostname` | `localhost` | Hostname/IP address where the keystone service runs ||
| `keystone_port` | `5000` | Keystone service port ||
| `keystone_protocol` | `http` | Desired keystone protocol (http/https) ||
| `rabbit_hostname` | `localhost` | Hostname/IP address where the RabbitMQ service runs ||
| `rabbit_username` | `rabbit_username_default` | RabbitMQ username for glance ||
| `rabbit_pass` | `rabbit_pass_default` | RabbitMQ password for glance. ||


Dependencies
------------

None.

Example Playbook
----------------

    - hosts: network001
      roles:
        - role: openstack-neutron_l3_agent
          rabbit_username: "openstack-neutron"
          rabbit_pass: "{{ RABBIT_NEUTRON_PASS }}"


---

A complete Ansible playbook demo, which uses this role, is available on Github (openstack-ansible-galaxy/vagrant-ansible-openstack) <https://github.com/openstack-ansible-galaxy/vagrant-ansible-openstack>

---


License
-------

Apache

Author Information
------------------

Davide Guerri - davide.guerri@gmail.com
