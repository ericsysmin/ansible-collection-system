# Ansible Collection - ericsysmin.system

Ansible collection that holds roles, that can be used to configure common system services.

## Roles

| Role      | Build Status                                                                                                                                                                                                                                                                                                                      | Documentation                                                                                          |
| --------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------ |
| chrony    | [![Role: ericsysmin.system.chrony Molecule Test](https://github.com/ericsysmin/ansible-collection-system/workflows/Role:%20ericsysmin.system.chrony%20Molecule%20Test/badge.svg)](https://github.com/ericsysmin/ansible-collection-system/actions?query=workflow%3A%22Role%3A+ericsysmin.system.chrony+Molecule+Test%22)          | [Documentation](https://github.com/ericsysmin/ansible-collection-system/blob/master/docs/chrony.md)    |
| epel      | [![Role: ericsysmin.system.epel Molecule Test](https://github.com/ericsysmin/ansible-collection-system/workflows/Role:%20ericsysmin.system.epel%20Molecule%20Test/badge.svg)](https://github.com/ericsysmin/ansible-collection-system/actions?query=workflow%3A%22Role%3A+ericsysmin.system.epel+Molecule+Test%22)                | [Documentation](https://github.com/ericsysmin/ansible-collection-system/blob/master/docs/epel.md)      |
| logrotate | [![Role: ericsysmin.system.logrotate Molecule Test](https://github.com/ericsysmin/ansible-collection-system/workflows/Role:%20ericsysmin.system.logrotate%20Molecule%20Test/badge.svg)](https://github.com/ericsysmin/ansible-collection-system/actions?query=workflow%3A%22Role%3A+ericsysmin.system.logrotate+Molecule+Test%22) | [Documentation](https://github.com/ericsysmin/ansible-collection-system/blob/master/docs/logrotate.md) |
| ntp       | [![Role: ericsysmin.system.ntp Molecule Test](https://github.com/ericsysmin/ansible-collection-system/workflows/Role:%20ericsysmin.system.ntp%20Molecule%20Test/badge.svg)](https://github.com/ericsysmin/ansible-collection-system/actions?query=workflow%3A%22Role%3A+ericsysmin.system.ntp+Molecule+Test%22)                   | [Documentation](https://github.com/ericsysmin/ansible-collection-system/blob/master/docs/ntp.md)       |
| remi_repo | [![Role: ericsysmin.system.remi_repo Molecule Test](https://github.com/ericsysmin/ansible-collection-system/workflows/Role:%20ericsysmin.system.remi_repo%20Molecule%20Test/badge.svg)](https://github.com/ericsysmin/ansible-collection-system/actions?query=workflow%3A%22Role%3A+ericsysmin.system.remi_repo+Molecule+Test%22) | [Documentation](https://github.com/ericsysmin/ansible-collection-system/blob/master/docs/remi_repo.md) |
| selinux   | [![Role: ericsysmin.system.selinux Molecule Test](https://github.com/ericsysmin/ansible-collection-system/workflows/Role:%20ericsysmin.system.selinux%20Molecule%20Test/badge.svg)](https://github.com/ericsysmin/ansible-collection-system/actions?query=workflow%3A%22Role%3A+ericsysmin.system.selinux+Molecule+Test%22)       | [Documentation](https://github.com/ericsysmin/ansible-collection-system/blob/master/docs/selinux.md)   |

## Testing

Testing is done through GitHub Actions, and can be tested locally as well. GitHub Actions can be located [here](https://github.com/ericsysmin/ansible-collection-system/actions).
Each workflow pertains to a single role, and can be launched locally using the following command:

```bash
MOLECULE_COMMAND={{ matrix.molecule_distro.command }} \
MOLECULE_DISTRO={{ matrix.molecule_distro.distro }} \
molecule --debug test -s {{ matrix.collection_role }}
```

To decide on the `MOLECULE_COMMAND` value please refer to the `.github/workflow/{{ collection_role }}.yml` file as it will have the value for proper systemd services.
