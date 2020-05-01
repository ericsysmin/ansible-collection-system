# Ansible Collection - ericsysmin.system

Ansible collection that holds roles, that can be used to configure common system services.

## Roles

| Role      | Build Status                                                                                                                                                                                                                                                        | Documentation                                                                                          |
| --------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------ |
| chrony    | [![Role: ericsysmin.system.chrony](https://github.com/ericsysmin/ansible-collection-system/workflows/ericsysmin.system.chrony/badge.svg)](https://github.com/ericsysmin/ansible-collection-system/actions?query=workflow%3A%22ericsysmin.system.chrony%22)          | [Documentation](https://github.com/ericsysmin/ansible-collection-system/blob/master/docs/chrony.md)    |
| epel      | [![Role: ericsysmin.system.epel](https://github.com/ericsysmin/ansible-collection-system/workflows/ericsysmin.system.epel/badge.svg)](https://github.com/ericsysmin/ansible-collection-system/actions?query=workflow%3A%22ericsysmin.system.epel%22)                | [Documentation](https://github.com/ericsysmin/ansible-collection-system/blob/master/docs/epel.md)      |
| logrotate | [![Role: ericsysmin.system.logrotate](https://github.com/ericsysmin/ansible-collection-system/workflows/ericsysmin.system.logrotate/badge.svg)](https://github.com/ericsysmin/ansible-collection-system/actions?query=workflow%3A%22ericsysmin.system.logrotate%22) | [Documentation](https://github.com/ericsysmin/ansible-collection-system/blob/master/docs/logrotate.md) |
| ntp       | [![Role: ericsysmin.system.ntp](https://github.com/ericsysmin/ansible-collection-system/workflows/ericsysmin.system.ntp/badge.svg)](https://github.com/ericsysmin/ansible-collection-system/actions?query=workflow%3A%22ericsysmin.system.ntp%22)                   | [Documentation](https://github.com/ericsysmin/ansible-collection-system/blob/master/docs/ntp.md)       |
| remi_repo | [![Role: ericsysmin.system.remi_repo](https://github.com/ericsysmin/ansible-collection-system/workflows/ericsysmin.system.remi_repo/badge.svg)](https://github.com/ericsysmin/ansible-collection-system/actions?query=workflow%3A%22ericsysmin.system.remi_repo%22) | [Documentation](https://github.com/ericsysmin/ansible-collection-system/blob/master/docs/remi_repo.md) |
| selinux   | [![Role: ericsysmin.system.selinux](https://github.com/ericsysmin/ansible-collection-system/workflows/ericsysmin.system.selinux/badge.svg)](https://github.com/ericsysmin/ansible-collection-system/actions?query=workflow%3A%22ericsysmin.system.selinux%22)       | [Documentation](https://github.com/ericsysmin/ansible-collection-system/blob/master/docs/selinux.md)   |

## Testing

Testing is done through GitHub Actions, and can be tested locally as well. GitHub Actions can be located [here](https://github.com/ericsysmin/ansible-collection-system/actions).
Each workflow pertains to a single role, and can be launched locally using the following command:

```bash
MOLECULE_COMMAND={{ matrix.molecule_distro.command }} \
MOLECULE_DISTRO={{ matrix.molecule_distro.distro }} \
molecule --debug test -s {{ matrix.collection_role }}
```

To decide on the `MOLECULE_COMMAND` value please refer to the `.github/workflow/{{ collection_role }}.yml` file as it will have the value for proper systemd services.
