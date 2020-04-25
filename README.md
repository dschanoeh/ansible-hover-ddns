# Ansible Role: hover-ddns


[![Build Status](https://travis-ci.com/dschanoeh/ansible-hover-ddns.svg?branch=master)](https://travis-ci.com/github/dschanoeh/ansible-hover-ddns)
![GitHub](https://img.shields.io/github/license/dschanoeh/ansible-hover-ddns)
![Ansible Role](https://img.shields.io/ansible/role/48002)

## Description
An Ansible role that installs the [hover-ddns]([a](https://github.com/dschanoeh/hover-ddns)) service and configures a systemd timer for its execution.

## Role Variables

| Name           | Default Value | Description                        |
| -------------- | ------------- | -----------------------------------|
| `hover_ddns_version` | latest | Version of hover-ddns to be installed. You can use 'latest' or e.g. 'v0.2.0'. Only versions > v0.2.0 are supported |
| `hover_ddns_binary_install_dir` | /usr/local/bin | Installation directory for the hover-ddns binary |
| `hover_ddns_config_file_path` | /etc/hover-ddns.yaml | Location of the config file |
| `hover_ddns_force_update` | false | Configuration option to force an update even when the public IP didn't change |
| `hover_ddns_username` | - | Your user name at hover |
| `hover_ddns_password` | - | Your hover password |
| `hover_ddns_domain` | - | The domain under which the host resides |
| `hover_ddns_hostname` | - | Hostname to create the DNS record for |
| `hover_ddns_disable_ipv4` | false | Disables handling of IPv4 |
| `hover_ddns_disable_ipv6` | false | Disables handling of IPv6 |
| `hover_ddns_dns_server` | 8.8.8.8:53 | Configures the DNS server to be used for lookups |
| `hover_ddns_public_ip_service` | opendns | Configures the public IP service to be used. Must be one of opendns, ipify, local_interface |
| `hover_ddns_interface_name` | eth0 | Interface to be used when the local_interface service is selected |

## Example

```yaml
---
- hosts: all
  roles:
  - dschanoeh.hover_ddns
  vars:
    hover_ddns_username: "YOUR_USER"
    hover_ddns_password: "YOUR_PASS"
    hover_ddns_domain: "YOUR_DOMAIN"
    hover_ddns_hostname: "YOUR_HOST"
```
