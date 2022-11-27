ClearBox
========

Ansible role that automates basic configuration of Debian servers.

Requirements
------------

This role was tested on Debian 11, but it should work on any Debian-based distro.

Role Variables
--------------

### Required

None (yet)

### Optional

- `desiredLocale` - If not empty, will be set as system default locale *(default: "")*
- `desiredTimezone` - If not empty, will be set as system timezone *(default: "")*
- `additionalPackages` - list of additional packages that you want to be installed on the system *(default: vim, ranger, pv, less, htop, dnsutils)*

Dependencies
------------

This role does not require other dependencies.

Example Playbook
----------------

```yaml
---
  hosts: all
  roles:
    - role: clearBox
      vars:
        - desiredLocale: pl_PL.UTF-8
        - desiredTimezone: Europe/Warsaw
      become: yes
```

License
-------

MIT

Author Information
------------------

Github: *[https://github.com/Array221](https://github.com/Array221)*
