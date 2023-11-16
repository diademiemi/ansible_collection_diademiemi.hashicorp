Ansible Role Vagrant
=========
[![Molecule test](https://github.com/diademiemi/ansible_collection_diademiemi.hashicorp/actions/workflows/ansible-role-vagrant.yml/badge.svg)](https://github.com/diademiemi/ansible_collection_diademiemi.hashicorp/actions/workflows/ansible-role-vagrant.yml)

This is an Ansible role to install Vagrant and Vagrant plugins.

Requirements
------------
These platforms are supported:
- Ubuntu 20.04  
- Ubuntu 22.04  
- Debian 10  
- Debian 11  
- EL 8 (Tested on Rocky Linux 8)  
- EL 9 (Tested on Rocky Linux 9)  
- Fedora 38  
- openSUSE Leap 15.5

<!--
- List hardware requirements here  
-->

Role Variables
--------------

Variable | Default | Description
--- | --- | ---
`vagrant_plugin_user` | `{{ ansible_user_id }}` | User to set up Vagrant plugins for
`vagrant_plugins` | `[]` | List of Vagrant plugins to install. See [defaults/main.yml](./defaults/main.yml) for examples.
<!--
`variable` | `default` | Variable example
`long_variable` | See [defaults/main.yml](./defaults/main.yml) | Variable referring to defaults
`distro_specific_variable` | See [vars/debian.yml](./vars/debian.yml) | Variable referring to distro-specific variables
-->

Dependencies
------------
<!-- List dependencies on other roles or criteria -->
None

Example Playbook
----------------

```yaml
- name: Use diademiemi.hashicorp.vagrant role
  hosts: "{{ target | default('vagrant') }}"
  roles:
    - role: "diademiemi.hashicorp.vagrant"
      tags: ['diademiemi', 'vagrant', 'setup']    ```

```

License
-------

MIT

Author Information
------------------

- diademiemi (@diademiemi)

Role Testing
------------

This repository comes with Molecule that run in Podman on the supported platforms.
Install Molecule by running

```bash
pip3 install -r requirements.txt
```

Run the tests with

```bash
molecule test
```

These tests are automatically ran by GitHub Actions on push. If the tests are successful, the role is automatically published to Ansible Galaxy.

