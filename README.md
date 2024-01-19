[![CI](https://github.com/de-it-krachten/ansible-role-sudo/workflows/CI/badge.svg?event=push)](https://github.com/de-it-krachten/ansible-role-sudo/actions?query=workflow%3ACI)


# ansible-role-sudo

Installs/configures sudo with optional hardening



## Dependencies

#### Roles
None

#### Collections
None

## Platforms

Supported platforms

- Red Hat Enterprise Linux 7<sup>1</sup>
- Red Hat Enterprise Linux 8<sup>1</sup>
- Red Hat Enterprise Linux 9<sup>1</sup>
- CentOS 7
- RockyLinux 8
- RockyLinux 9
- OracleLinux 8
- OracleLinux 9
- AlmaLinux 8
- AlmaLinux 9
- SUSE Linux Enterprise 15<sup>1</sup>
- openSUSE Leap 15
- Debian 11 (Bullseye)
- Debian 12 (Bookworm)
- Ubuntu 20.04 LTS
- Ubuntu 22.04 LTS
- Fedora 37
- Fedora 38

Note:
<sup>1</sup> : no automated testing is performed on these platforms

## Role Variables
### defaults/main.yml
<pre><code>
# List of audi packages
sudo_packages:
  - sudo

# Sudo log file
sudo_logfile: /var/log/sudo.log

# Timeout before re-authentication
sudo_timestamp_timeout: 5

# Perform sudo hardening rules (CIS1/2)
sudo_hardening: false
</pre></code>




## Example Playbook
### molecule/default/converge.yml
<pre><code>
- name: sample playbook for role 'sudo'
  hosts: all
  become: 'yes'
  vars:
    sudo_hardening: true
  tasks:
    - name: Include role 'sudo'
      ansible.builtin.include_role:
        name: sudo
</pre></code>
