gvm
=====

[![Build Status](https://travis-ci.org/suzuki-shunsuke/ansible-gvm.svg?branch=master)](https://travis-ci.org/suzuki-shunsuke/ansible-gvm)

Install [gvm](https://github.com/moovweb/gvm).

Requirements
------------

* [motemen/ghq](https://github.com/motemen/ghq)

Role Variables
--------------

* ghq_executable: The ghq command path. The default is "ghq".

Dependencies
------------

* [suzuki-shunsuke.ghq-module](https://galaxy.ansible.com/suzuki-shunsuke/ghq-module/)

Example Playbook
----------------

```yaml
- hosts: servers
  roles:
  - role: suzuki-shunsuke.gvm
    ghq_executable: "{{ansible_env.HOME}}/.go/bin/ghq"
```

License
-------

MIT
