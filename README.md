[![Actions Status - Main](https://github.com/juju4/ansible-upgrade-pkgs/workflows/AnsibleCI/badge.svg)](https://github.com/juju4/ansible-upgrade-pkgs/actions?query=branch%3Amain)
[![Actions Status - Devel](https://github.com/juju4/ansible-upgrade-pkgs/workflows/AnsibleCI/badge.svg?branch=devel)](https://github.com/juju4/ansible-upgrade-pkgs/actions?query=branch%3Adevel)

# upgrade-pkgs ansible role

Ansible role to do upgrade system with packaging system
Tentative support for Debian and Redhat-based distribution, Alpine Linux, Darwin/Macports, OpenBSD.

If Aide HIDS is present, it will be updated
If reboot is needed, it will be done unless flagged noreboot or if ubuntu livepatch is enabled.

## Requirements & Dependencies

### Ansible
It was tested on the following versions:
 * 2.2
 * 2.5

### Operating systems

Ubuntu 18.04, 20.04, 22.04 and Centos7

## Example Playbook

Just include this role in your list.
For example

```
- host: all
  roles:
    - juju4.upgrade-pkgs
```

## Variables

Nothing specific for now.

## Continuous integration

This role has a travis basic test (for github), more advanced with kitchen and also a Vagrantfile (test/vagrant).
Default kitchen config (.kitchen.yml) is lxd-based, while (.kitchen.vagrant.yml) is vagrant/virtualbox based.

Once you ensured all necessary roles are present, You can test with:
```
$ gem install kitchen-ansible kitchen-lxd_cli kitchen-sync kitchen-vagrant
$ cd /path/to/roles/juju4.upgrade-pkgs
$ kitchen verify
$ kitchen login
$ KITCHEN_YAML=".kitchen.vagrant.yml" kitchen verify
```
or
```
$ cd /path/to/roles/juju4.upgrade-pkgs/test/vagrant
$ vagrant up
$ vagrant ssh
```


## Troubleshooting & Known issues

N/A

## See also

* https://access.redhat.com/discussions/3155941, https://github.com/Tronde/ansible-role-rhel-patchmanagement

## License

BSD 2-clause
