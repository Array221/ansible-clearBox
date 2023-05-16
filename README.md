ClearBox
========

Ansible role that automates basic configuration of Debian servers. This includes:
- Updating all system packages
- Setting up system default language
- Setting up system timezone
- Creating non-root user with sudo priviledges and given SSH keys
- Hardening SSH configuration

Requirements
------------

This role was tested on Debian 11, but it should work on any Debian-based distro.

Role Variables
--------------

### Required

- `sudoUser` - Name of admin user that will be created *(Can't be equal to root)*

### Optional

- `sshKeysLink` - Link to SSH keys that will be added to sudo user *(default: None)*
- `desiredLocale` - Default system locale that will be set in system *(default: None)*
- `desiredTimezone` - Timezone that will be set in system *(default: None)*
- `enableSilentLogin` - Enables silent login for admin user *(default: true)*
- `sshPort` - SSH port number that will be set *(default: 22)*
- `sshMaxAuthTries` - Maximum number of login tries before disconnecting *(default: 5)*
- `sshGatewayPorts` - Status of GatewayPorts option *(default: false)*
- `sshPermitTunnel` - Status of PermitTunnel option *{default: false)*
- `sshBanner` - SSH banner *(default: None)*
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
    - role: array221.clearbox
      vars:
        - sudoUser: sudoAdmin
        - sshKeysLink: https://github.com/Array221.keys
        - desiredLocale: pl_PL.UTF-8
        - desiredTimezone: Europe/Warsaw
        - sshPort: 122
        - sshMaxAuthTries: 3
        - sshBanner: Welcome to test server!
      become: yes
```

License
-------

MIT

Author Information
------------------

Github: *[https://github.com/Array221](https://github.com/Array221)*
