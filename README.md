![Build Status](https://img.shields.io/gitlab/pipeline-status/mireiawenrose/ansible-roles/resolv.conf?branch=master&style=plastic) [![Ansible Galaxy](https://img.shields.io/badge/Ansible%20Galaxy-mireiawen.resolvconf-blueviolet?style=plastic)](https://galaxy.ansible.com/mireiawen/resolvconf)

# Ansible resolv.conf

Setup entries in resolv.conf file (/etc/resolv.conf)


## Requirements

Access to edit the `/etc/resolv.conf` file.

## Role Variables

 Configuration key    | Description                        | Default value               
----------------------|------------------------------------|----------------------
 `dns_nameservers`    | Array of DNS server addresses      | ```- "127.0.0.1"```
 `dns_domain`         | The DNS domain to use              | `localdomain`
 `dns_search_domains` | Array of the DNS search domains    | ```- "localdomain"```
 `dns_resolvconf`     | The path to the `resolv.conf` file | `/etc/resolv.conf`

## Dependencies

None.

## Example Playbook

```yaml
- hosts: "servers"
  roles:
  - role: "mireiawen.resolvconf"
    dns_nameservers:
    - "1.1.1.1"
    - "8.8.8.8"
    dns_domain: "localdomain.tld"
    dns_search_domains:
    - "localdomain.tld"
    - "sub.localdomain.tld"
    - "example.local"
```

## License
MIT, see `LICENSE`
