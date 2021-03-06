# ansible-gvm

[![Build Status](https://github.com/suzuki-shunsuke/ansible-gvm/workflows/CI/badge.svg)](https://github.com/suzuki-shunsuke/ansible-gvm/actions)
[![GitHub last commit](https://img.shields.io/github/last-commit/suzuki-shunsuke/ansible-gvm.svg)](https://github.com/suzuki-shunsuke/ansible-gvm)
[![License](http://img.shields.io/badge/license-mit-blue.svg?style=flat-square)](https://raw.githubusercontent.com/suzuki-shunsuke/ansible-gvm/master/LICENSE)

Ansible Role to install [gvm](https://github.com/moovweb/gvm)

This role is based on [the official gvm-installer](https://github.com/moovweb/gvm/blob/master/binscripts/gvm-installer).

> ## Notice: GVM == Go (Not Groovy) Version Manager
> This role has nothing to do with [Groovy enVironment Manager](http://sdkman.io/).

## Requirements

* Git

## Role Variables

name | required | default | description
--- | --- | --- | ---
gvm_root | no | `$HOME/.gvm` |
gvm_goroot | no | `undefined` |
gvm_is_dependencies_installed | no | no | By default build dependencies are not installed
gvm_rc_path | no | "NOT ADD" | By default configuration is not added
gvm_repo | no | https://github.com/moovweb/gvm |
gvm_version | no | HEAD |
gvm_update | no | yes |
gvm_darwin_build_dependencies | no | see [defaults/main.yml](https://github.com/suzuki-shunsuke/ansible-gvm/blob/master/defaults/main.yml) | If gvm_is_dependencies_installed is "no" this is ignored
gvm_redhat_build_dependencies | no | see [defaults/main.yml](https://github.com/suzuki-shunsuke/ansible-gvm/blob/master/defaults/main.yml) | If gvm_is_dependencies_installed is "no" this is ignored
gvm_debian_build_dependencies | no | see [defaults/main.yml](https://github.com/suzuki-shunsuke/ansible-gvm/blob/master/defaults/main.yml) | If gvm_is_dependencies_installed is "no" this is ignored

About build dependencies, see also [here](https://github.com/moovweb/gvm#mac-os-x-requirements).

## Dependencies

Nothing.

## Example Playbook

```yaml
- hosts: servers
  roles:
    - role: suzuki-shunsuke.gvm
      gvm_root: "{{ ansible_env.HOME }}/.ghq/github.com/moovweb/gvm"
      gvm_is_dependencies_installed: yes
      gvm_rc_path: "{{ ansible_env.HOME }}/.bashrc"
      gvm_darwin_build_dependencies:
        - readline
      gvm_version: 1.0.22
      gvm_update: no
```

## Change Log

See [Releases](https://github.com/suzuki-shunsuke/ansible-gvm/releases).

## See also

* [suzuki-shunsuke.gvm-module](https://github.com/suzuki-shunsuke/ansible-gvm-module): ansible module to run `gvm` command

## License

[MIT](LICENSE)
