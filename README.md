# ansible-mock-role

[![CircleCI](https://img.shields.io/circleci/project/uchida/ansible-mock-role.svg)](https://circleci.com/gh/uchida/ansible-mock-role)
[![License](https://img.shields.io/github/license/uchida/ansible-mock-role.svg)](http://creativecommons.org/publicdomain/zero/1.0/deed)

role to install mock, clean room package builder for RedHat Enterprise Linxu derivative distributions.
In addition, this role add user to mock group and initialize chroot repository.

## Role Variables

Available variables are listed below, along with default values:

```yaml
mock_config: fedora-rawhide-x86_64
mock_user: mock
```

`mock_config` is a variable to specify mock configuration name in /etc/mock.

`mock_user` is a variable to specify user to be add in the `mock` group

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

dedicated to public domain by [contributors](https://github.com/uchida/ansible-mock-role/graphs/contributors).
