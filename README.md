# Ansible Role: SMTP to Telegram

[![ubuntu-18](https://img.shields.io/badge/ubuntu-18.x-orange?style=flat&logo=ubuntu)](https://ubuntu.com/)
[![ubuntu-20](https://img.shields.io/badge/ubuntu-20.x-orange?style=flat&logo=ubuntu)](https://ubuntu.com/)
[![debian-9](https://img.shields.io/badge/debian-9.x-orange?style=flat&logo=debian)](https://www.debian.org/)
[![debian-10](https://img.shields.io/badge/debian-10.x-orange?style=flat&logo=debian)](https://www.debian.org/)
[![centos-7](https://img.shields.io/badge/centos-7.x-orange?style=flat&logo=centos)](https://www.centos.org/)
[![centos-8](https://img.shields.io/badge/centos-8.x-orange?style=flat&logo=centos)](https://www.centos.org/)

[![License](https://img.shields.io/badge/license-MIT%20License-brightgreen.svg?style=flat)](https://opensource.org/licenses/MIT)
[![GitHub issues](https://img.shields.io/github/issues/OnkelDom/ansible-role-smtp-to-telegram?style=flat)](https://github.com/OnkelDom/ansible-role-smtp-to-telegram/issues)
[![GitHub tag](https://img.shields.io/github/tag/OnkelDom/ansible-role-smtp-to-telegram.svg?style=flat)](https://github.com/OnkelDom/ansible-role-smtp-to-telegram/tags)
[![GitHub action](https://github.com/OnkelDom/ansible-role-smtp-to-telegram/workflows/ansible-lint/badge.svg)](https://github.com/OnkelDom/ansible-role-smtp-to-telegram)

## Description

Deploy [SMTP to Telegram](https://github.com/OnkelDom/ansible-role-smtp-to-telegram) using ansible.

## Dependencys

This role depens on ansible-role-prometheus

## Requirements

- Ansible >= 2.9 (It might work on previous versions, but we cannot guarantee it)
- Community Packages: `ansible-galaxy collection install community.general`

## Role Variables

All variables which can be overridden are stored in [defaults/main.yml](defaults/main.yml) file as well as in table below.

| Name           | Default Value | Description                        |
| -------------- | ------------- | -----------------------------------|
| `proxy_env` |  {} | Set proxy environment variables |
| `smtp_to_telegram_version` | 1.0.3 | app version |
| `smtp_to_telegram_allow_firewall` | false | allow firewall access |
| `smtp_to_telegram_binary_install_dir` | /usr/local/bin | binary install dir |
| `smtp_to_telegram_system_user` | prometheus | default user |
| `smtp_to_telegram_system_group` | prometheus | deefault group |
| `smtp_to_telegram_listen_address` | 0.0.0.0 | default listen address |
| `smtp_to_telegram_listen_port` | 8888 | default listen port |
| `smtp_to_telegram_primary_host` | "{{ ansible_hostname }}.{{ ansible_domain }}" | message default hostname |
| `smtp_to_telegram_api_prefix` | "" | https://api.telegram.org |
| `smtp_to_telegram_bot_token` | ""  | telegram bot token |
| `smtp_to_telegram_chat_ids` | "" | comma seperated chat ids |
| `smtp_to_telegram_message_max_length` | 0 | message max length - default 0 = unlimited |
| `smtp_to_telegram_message_template` | "From: {from}\\nTo: {to}\\nSubject: {subject}\\n\\n{body}" | message template |
| `smtp_to_telegram_http_proxy` | "" | proxy to send to telegram |
| `smtp_to_telegram_https_proxy` | "" | proxy to send to telegram |

## Example

### Playbook

```yaml
---
- hosts: all
  roles:
  - onkeldom.smtp_to_telegram
```

## Contributing

See [contributor guideline](CONTRIBUTING.md).

## License

This project is licensed under MIT License. See [LICENSE](/LICENSE) for more details.
