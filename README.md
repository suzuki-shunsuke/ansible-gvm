# ansible-gvm

[![Build Status](https://travis-ci.org/suzuki-shunsuke/ansible-gvm.svg?branch=master)](https://travis-ci.org/suzuki-shunsuke/ansible-gvm)

ansible role to install [gvm](https://github.com/moovweb/gvm)

## Requirements

* git

## Role Variables

name | required | default | description
--- | --- | --- | ---
gvm_root | no | $GVM_ROOT >> $HOME/.gvm
gvm_is_dependencies_installed | no | no | By default build dependencies are not installed
gvm_rc_path | no | "NOT ADD" | By default configuration is not added
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
```

## License

[MIT](LICENSE)
