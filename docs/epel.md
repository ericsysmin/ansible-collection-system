# ericsysmin.system.epel

Role to install EPEL on RHEL systems

## Requirements

None

## Role Variables

| Variable      | Default | Comments |
| ------------- | ------- | -------- |
| `epel_manual` | `false` |          |

### Vars used if `epel_manual == true`

| Variable                             | Default                                                                                                                 | Comments |
| ------------------------------------ | ----------------------------------------------------------------------------------------------------------------------- | -------- |
| `epel_repo_gpg_key_url`              | `http://download.fedoraproject.org/pub/epel/RPM-GPG-KEY-EPEL-{{ ansible_distribution_major_version }}`                  |          |
| `epel_repo_gpg_key_url`              | `<http://download.fedoraproject.org/pub/epel/RPM-GPG-KEY-EPEL-{{> ansible_distribution_major_version }}"`               |          |
| `epel_repo_gpg_key_file`             | `/etc/pki/rpm-gpg/RPM-GPG-KEY-EPEL-{{ ansible_distribution_major_version }}"`                                           |          |
| `epel_repo_url`                      | `https://dl.fedoraproject.org/pub/epel/epel-release-latest-{{ ansible_distribution_major_version }}.noarch.rpm"`        |          |
| `epel_repofile_path`                 | `/etc/yum.repos.d/epel.repo`                                                                                            |          |
| `epel_repo_use_baseurl`              | `false`                                                                                                                 |          |
| `epel_repo_baseurl`                  | `<http://download.fedoraproject.org/pub/epel/{{> ansible_distribution_major_version }}/$basearch`                       |          |
| `epel_repo_metalink`                 | `<https://mirrors.fedoraproject.org/metalink?repo=epel-{{> ansible_distribution_major_version }}&arch=$basearch`        |          |
| `epel_repo_failovermethod`           | `priority`                                                                                                              |          |
| `epel_repo_gpgcheck`                 | `true`                                                                                                                  |          |
| `epel_repo_enabled`                  | `true`                                                                                                                  |          |
| `epel_repo_gpgkey`                   | `file://{{ epel_repo_gpg_key_file }}`                                                                                   |          |
| `epel_debuginfo_repo_use_baseurl`    | `false`                                                                                                                 |          |
| `epel_debuginfo_repo_baseurl`        | `<http://download.fedoraproject.org/pub/epel/{{> ansible_distribution_major_version }}/$basearch/debug`                 |          |
| `epel_debuginfo_repo_metalink`       | `<https://mirrors.fedoraproject.org/metalink?repo=epel-debug-{{> ansible_distribution_major_version }}&arch=$basearch`  |          |
| `epel_debuginfo_repo_failovermethod` | `priority`                                                                                                              |          |
| `epel_debuginfo_repo_gpgcheck`       | `true`                                                                                                                  |          |
| `epel_debuginfo_repo_enabled`        | `false`                                                                                                                 |          |
| `epel_debuginfo_repo_gpgkey`         | `file://{{ epel_repo_gpg_key_file }}`                                                                                   |          |
| `epel_source_repo_use_baseurl`       | `false`                                                                                                                 |          |
| `epel_source_repo_baseurl`           | `<http://download.fedoraproject.org/pub/epel/{{> ansible_distribution_major_version }}/SRPMS`                           |          |
| `epel_source_repo_metalink`          | `<https://mirrors.fedoraproject.org/metalink?repo=epel-source-{{> ansible_distribution_major_version }}&arch=$basearch` |          |
| `epel_source_repo_failovermethod`    | `priority`                                                                                                              |          |
| `epel_source_repo_gpgcheck`          | `true`                                                                                                                  |          |
| `epel_source_repo_enabled`           | `false`                                                                                                                 |          |
| `epel_source_repo_gpgkey`            | `file://{{ epel_repo_gpg_key_file }}`                                                                                   |          |

## Dependencies

None

## Example Playbook

Including an example of how to use your role (for instance, with variables
passed in as parameters) is always nice for users too:

```yaml
- hosts: servers
  roles:
    - role: ericsysmin.system.epel
```

```yaml
- hosts: all
  roles:
    - role: ericsysmin.system.epel
      epel_manual: true
      epel_repo_use_baseurl: true
```

## License

MIT

## Author Information

[ericsysmin](https://ericsysmin.com)
