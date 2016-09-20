# git

[![License](https://img.shields.io/badge/license-New%20BSD-blue.svg?style=flat)](https://raw.githubusercontent.com/ansiblebit/git/master/LICENSE)
[![Build Status](https://travis-ci.org/ansiblebit/git.svg?branch=master)](https://travis-ci.org/ansiblebit/git)

[![Platform](http://img.shields.io/badge/platform-centos-932279.svg?style=flat)](#)
[![Platform](http://img.shields.io/badge/platform-ubuntu-dd4814.svg?style=flat)](#)

[![Project Stats](https://www.openhub.net/p/ansiblebit-git/widgets/project_thin_badge.gif)](https://www.openhub.net/p/ansiblebit-git/)

[Ansible][ansible] role to install [git][git].


## Tests

| Family | Distribution | Version | Test Status |
|:-:|:-:|:-:|:-:|
| Debian | Debian  | Jessie  | [![x86_64](http://img.shields.io/badge/x86_64-passed-006400.svg?style=flat)](#) |
| Debian | Debian  | Wheezy  | [![x86_64](http://img.shields.io/badge/x86_64-passed-006400.svg?style=flat)](#) |
| Debian | Ubuntu  | Yakkety | [![x86_64](http://img.shields.io/badge/x86_64-passed-006400.svg?style=flat)](#) |
| Debian | Ubuntu  | Xenial  | [![x86_64](http://img.shields.io/badge/x86_64-passed-006400.svg?style=flat)](#) |
| Debian | Ubuntu  | Vivid   | [![x86_64](http://img.shields.io/badge/x86_64-passed-006400.svg?style=flat)](#) |
| Debian | Ubuntu  | Trusty  | [![x86_64](http://img.shields.io/badge/x86_64-passed-006400.svg?style=flat)](#) |
| Debian | Ubuntu  | Precise | [![x86_64](http://img.shields.io/badge/x86_64-passed-006400.svg?style=flat)](#) |
| RedHat | Centos  | 7       | [![x86_64](http://img.shields.io/badge/x86_64-passed-006400.svg?style=flat)](#) |
| RedHat | CentOS  | 6.6     | [![x86_64](http://img.shields.io/badge/x86_64-passed-006400.svg?style=flat)](#) |
| RedHat | CentOS  | 6.4     | [![x86_64](http://img.shields.io/badge/x86_64-passed-006400.svg?style=flat)](#) |


## Requirements

Any pre-requisites that may not be covered by Ansible itself or the role should be mentioned here.
For instance, if the role uses the EC2 module,
it may be a good idea to mention in this section that the boto package is required.

- ansible >= 2.0


## Role Variables

- **debug**: flag to run debug tasks.
- **git_build_dependencies**: list of build dependencies.
- **git_dir_src**: directory where to store the [git][git] source.
- **git_path**: the directory where to install [git][git].
- **git_prefix**: the filename prefix of the [git][git] tarball.
- **git_tarball**: the filename for the [git][git] tarball.
- **git_version**: the version to be installed.


## Dependencies

None.


## Playbooks

    - hosts: servers
      vars:
        git_version: 1.9.1

      roles:
         - role: ansiblebit.git


## Tags

- **configuration**: configuration tasks.
- **debug**: task to debug role variables.
- **installation**: installation tasks.
- **validation**: task to validate role variables.


## Test

To run the tests you will need to install:

- [tox](https://tox.readthedocs.org/)
- [vagrant](https://www.vagrantup.com/)

To run all tests against all pre-defined OS/distributions * ansible versions:

```
$ tox
```

To run tests for `trusty64`:

```
$ cd tests
$ bash test_idempotence.sh --box trusty64.vagrant.dev
# log file will be stores under tests/log
```

To perform debugging on a specific environment:

```
$ cd tests
$ vagrant up trusty64.vagrant.dev

# to provision using the test.yml playbook (as many time as you need)
$ vagrant provision trusty64.vagrant.dev

# to access the Vagrant box
$ vagrant ssh trusty64.vagrant.dev
```


## Author Information

- [steenzout][steenzout]


[ansible]:  https://ansible.com/    "Ansible"
[git]:  https://git-scm.com/    "git"
[steenzout]:    https://github.com/steenzout/   "Pedro Salgado"
