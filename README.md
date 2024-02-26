# ansible-debian-12-hardening

[![Actively Maintained](https://img.shields.io/badge/Maintenance%20Level-Actively%20Maintained-green.svg)](https://gist.github.com/cheerfulstoic/d107229326a01ff0f333a1d3476e068d)

This role applies security hardening configurations to systems running Debian 12 (Bookworm). These configurations include:

* AppArmor
* Apt Package Manager
* Auditd + LAUREL
* Fail2Ban
* Kernel tuning
* Lynis security audit
* OpenSSH
* UFW Firewall

Some of these configurations can be enabled/disabled in `defaults/main.yml`. Please make sure to edit at least all variables with  `__edit_me__` placeholder in `defaults/main.yml`.

After applying the configurations, a Lynis security audit is performed and a report is sent to an e-mail address defined in `defaults/main.yml`.

## Requirements
Requires Ansible 2.10 or later.

## Role Variables
A large number of settings and configurations can be found in defaults/main.yml.

## Dependencies
None

## Example Playbook

    - hosts: all
      become: yes
      become_method: sudo
      roles:
        - ansible-debian-12-xyz

## Example Inventory

*inventory.yml*

    ---
    servers:
      hosts:
        192.168.0.11:
          ansible_ssh_user: admin
          machine_hostname: server01
        192.168.0.12:
          ansible_ssh_user: admin
          machine_hostname: server02
        192.168.0.13:
          ansible_ssh_user: admin
          machine_hostname: server03

## License
GPL-3.0 License

## Author Information
This role was created by Michael Houben, based on <https://github.com/dan-kir/ansible-debian-11-hardening> by Dan Kir
