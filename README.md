# uchida.mock

[![Ansible Role](https://img.shields.io/ansible/role/6101.svg?maxAge=2592000)](https://galaxy.ansible.com/detail#/role/6101)
![Version](https://img.shields.io/github/tag/uchida/ansible-mock-role.svg?maxAge=2592000)
[![License](https://img.shields.io/github/license/uchida/ansible-mock-role.svg?maxAge=2592000)](https://tldrlegal.com/license/creative-commons-cc0-1.0-universal)
[![Travis](https://img.shields.io/travis/uchida/ansible-mock-role.svg?maxAge=2592000)](https://travis-ci.org/uchida/ansible-mock-role)

ansible role to install mock, clean room package builder for RedHat Enterprise Linux derivative distributions.
In addition, this role add user to mock group and initialize chroot repository.

## Role Variables

Available role variables are listed below, along with default values:

```yaml
mock_config: ''
mock_user: mock
```

`mock_config` is a variable to specify mock configuration name in /etc/mock.
if this variable is specified, create mock repository. default `''` no mock repository created.

`mock_user` is a variable to specify user to be add in the `mock` group.

## Example Playbooks

install mock and add vagrant user to mock group and initialize epel-6-x86_64 repository

```yaml
- hosts: servers
  roles:
  - role: uchida.mock
    mock_config: epel-6-x86_64
    mock_user: vagrant
```

install mock and add vagrant user to mock group and initialize fedora-rawhide-x86_64, epel-7-x86_64 and epel-6-x86_64 repositories.

```yaml
- hosts: servers
  roles:
  - role: uchida.mock
    mock_user: vagrant
  - role: uchida.mock
    mock_config: fedora-rawhide-x86_64
    mock_user: vagrant
  - role: uchida.mock
    mock_config: epel-7-x86_64
    mock_user: vagrant
  - role: uchida.mock
    mock_config: epel-6-x86_64
    mock_user: vagrant
```

## License

[![CC0](http://i.creativecommons.org/p/zero/1.0/88x31.png "CC0")](http://creativecommons.org/publicdomain/zero/1.0/deed)

dedicated to public domain, no rights reserved.
