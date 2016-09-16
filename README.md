# Ansible Role: redis

[![Build Status](https://travis-ci.org/AttestationLegale/ansible-role-redis.svg?branch=master)](https://travis-ci.org/AttestationLegale/ansible-role-redis) [![Ansible Galaxy](http://img.shields.io/badge/ansible--galaxy-redis-blue.svg)](https://galaxy.ansible.com/AttestationLegale/redis/)

The redis role allows you to create dedicated instances running under a specified user/group.

This role performs the following tasks:

  - download and exrtact redis in /opt/redis/{{ version }}
  - push /home/{{ user }}/etc/redis.conf
  - push /home/{{ user }}/bin/redis # startup script


## Requirements

### User

The user hosting the redis instance must exist on the target system.

You can use [AttestationLegale.skel](https://galaxy.ansible.com/AttestationLegale/skel/) and [AttestationLegale.users](https://galaxy.ansible.com/AttestationLegale/users/) to create all the necessary stuff before calling redis role.

## Role Variables

For a complete list of variables, see `default/main.yml`.

    redis_instances: []

## Dependencies

None

## Example Playbook

```yaml
---
  - hosts: all
    roles:
      - redis
    vars:
      - redis_instances:
        - owner: foo
          group: bar
          home: /home/foo
          version: 3.0.7
          config: []
```

## License

MIT / BSD

## Author Information

This role was created in 2016 by [ALG](https://www.attestationlegale.fr)
