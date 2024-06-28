Set Transmitted Power Level Role
================================

As a demonstration of NETCONF for Microwave, this Ansible role position the
Microwave transmit power to a fixed value. **Not intented to provide real usage.**

Role Variables
--------------

This demonstrator use only 2 settable variables: `interface` and `power`.

| Parameter    | Type   | Required | Example     | Comments                                                                   |
|--------------|--------|----------|-------------|----------------------------------------------------------------------------|
| `interface`  | string | Yes      | CT-13-255-1 | The interface name for which power will be configured.                     |
| `power`      | float  | Yes      | -4.2        | The desired transmit power, in dBm. Range -99..99 with 0.1 dBm resolution. |


Dependencies
------------

The [`ansible.netcommon`](https://galaxy.ansible.com/ui/repo/published/ansible/netcommon/)
collection is required, because the module
[`netconf_config`](https://docs.ansible.com/ansible/latest/collections/ansible/netcommon/netconf_config_module.html)
is used.

Example Playbook
----------------

Here is a fully functional playbook:
```yaml
---
- name: Test NETCONF on Microwave links by setting transmitted power level
  hosts: my_microwave_ne

  roles:

    - role: power
      vars:
        interface: CT-13-255-1
        power: -4.2
```

The [test_ansible](https://github.com/jrebiffe/test_ansible) repository
usable as project on AWX.

License
-------

MIT

Author Information
------------------

Jean Rebiffe, Orange Innovation Networks
