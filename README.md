# Ansible role: ss_rust

[![MIT licensed][mit-badge]][mit-link]
[![Galaxy Role][role-badge]][galaxy-link]

Description
----

Ansible role for Shadowsocks-rust automated installation and configuration.

Requirements
----

One of the following OS (or deriviatives):

 - Ubuntu | [Raspberry Pi OS][rpi-os-link] | Raspbian | [Minibian][minibian-link]
 - CentOS
    - 7
    - 8
    - 9
 - Debian
    - jessie
    - stretch
    - buster
    - bullseye

Role Variables
----

OS-Agnostic:

| Variable | Description | Default |
|----------|-------------|---------|
| `ss_rust.vers` | shadowsocks-rust version | `v1.14.3` |
| `ss_rust.arch` | shadowsocks-rust binary architecture | `aarch64` |
| `ss_rust.dist` | distribution ss to be installed to | `unknown-linux-gnu` |
| `ss_rust.repo` | shadowsocks-rust source repository | `https://github.com/shadowsocks/shadowsocks-rust/releases/download` |
| `ss_rust.checksum` | checksum for ss file integrity validation | `sha256:fdd27edefd932bb82c18e3b6d1a48813f16d599dbd061e45d1ce20907de09fce` |
| `ss_rust_file` | shadowsocks-rust archive filename | see [`defaults/main.yml`](defaults/main.yml) |
| `ss_rust_link` | shadowsocks-rust download link | see [`defaults/main.yml`](defaults/main.yml) |
| `ss_rust_bin` | path to ss binaries to be installed on target | `/usr/local/bin` |
| `ss_rust_etc` | path to ss config file on target | `/etc/shadowsocks-rust.config.json` |
| `ss_rust_config[]` | List of maps containing server configuration stanzas to be converted into shadowsocks native json config | see [`defaults/main.yml`](defaults/main.yml) |

Dependencies
----

None

Example Playbook
----

```yaml
- hosts: shadowsocks
  roles:
    - drew1kun.ss_rust
```

License
----

[MIT][mit-link]

Author Information
----

Andrew Shagayev | [e-mail](mailto:drewshg@gmail.com)

[role-badge]: https://img.shields.io/badge/role-drew1kun.ss_rust-green.svg
[galaxy-link]: https://galaxy.ansible.com/drew1kun/ss_rust/
[mit-badge]: https://img.shields.io/badge/license-MIT-blue.svg
[mit-link]: https://raw.githubusercontent.com/drew1kun/ansible-ss_rust/master/LICENSE
[minibian-link]: https://minibianpi.wordpress.com/
[rpi-os-link]: https://www.raspberrypi.com/software/operating-systems/
