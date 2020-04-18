# Ansible Role: hover-ddns


[![Build Status](https://travis-ci.com/dschanoeh/ansible-hover-ddns.svg?branch=master)](https://travis-ci.com/github/dschanoeh/ansible-hover-ddns)
![GitHub](https://img.shields.io/github/license/dschanoeh/ansible-hover-ddns)
![Ansible Role](https://img.shields.io/ansible/role/48002)

## Description
An Ansible role that installs the [hover-ddns]([a](https://github.com/dschanoeh/hover-ddns)) service and configures a systemd timer for its execution.

## Role Variables

| Name           | Default Value | Description                        |
| -------------- | ------------- | -----------------------------------|
| `hover_ddns_version` | latest | Version of hover-ddns to be installed. You can use 'latest' or e.g. 'v0.1.0' |
| `hover_ddns_binary_install_dir` | /usr/local/bin | Installation directory for the hover-ddns binary |
| `hover_ddns_config_file_path` | /etc/hover-ddns.yaml | Location of the config file |
| `hover_ddns_force_update` | false | Configuration option to force an update even when the public IP didn't change |
| `hover_ddns_username` | - | Your user name at hover |
| `hover_ddns_password` | - | Your hover password |
| `hover_ddns_domain` | - | The domain under which the host resides |
| `hover_ddns_hostname` | - | Hostname to create the DNS record for |

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
