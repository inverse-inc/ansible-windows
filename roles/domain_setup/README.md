# Ansible domain-setup role

Will create a branch new domain on a Windows Server. This role is just a
basic bare bones roles to create the domain. No hardening or secure practices
are really included here.

## Requirements

N/A

## Variables

### Mandatory Variables

* `domain_setup__network_name`: The name of the Windows network interface that the domain will set itself as the primary DNS server.
* `domain_setup__domain_name`: The FQDN of the domain to create
* `domain_setup__safe_mode_password`: The password to set as the safe mode admin password when creating the domain
* `domain_setup__username`: A domain account name to create that is a member of the `Domain Admins` group
* `domain_setup__password`: The password for `domain_setup__username`

## Examples

```
- name: create domain controller for the domain domain.local
  hosts: all
  vars:
    domain_setup__network_name: Ethernet
    domain_setup__domain_name: domain.local
    domain_setup__safe_mode_password: Password01
    domain_setup__username: domain-user
    domain_setup__password: Password01
```
