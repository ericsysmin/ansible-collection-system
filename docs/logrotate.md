# ericsysmin.system.logrotate

[![Build Status](https://travis-ci.org/ericsysmin/ansible-role-logrotate.svg?branch=master)](https://travis-ci.org/ericsysmin/ansible-role-llogrotate)

This role installs logrotate on linux systems.

## Requirements

None

## Role Variables

| Variable             | Required | Default             | Comments                                   |
| -------------------- | -------- | ------------------- | ------------------------------------------ |
| `logrotate_install`  | No       | `true`              | Install package true/false                 |
| `logrotate_conf_dir` | No       | `/etc/logrotate.d/` | Configuration directory of logrotate files |
| `logrotate_files`    | No       | `[]`                | List of the logrotate files to be created  |

## Dependencies

None

## Example Playbook

```yaml
- hosts: servers
  roles:
    - role: ericsysmin.system.logrotate
      logrotate_files:
        - name: rails
          path: "/var/log/service_logs"
          options:
            - weekly
            - size 25M
            - missingok
            - compress
            - delaycompress
            - copytruncate
```

## License

MIT

## Author Information

[ericsysmin](https://ericsysmin.com)
