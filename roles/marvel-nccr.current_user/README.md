[![Build Status](https://travis-ci.org/marvel-nccr/ansible-role-current-user.svg?branch=master)](https://travis-ci.org/marvel-nccr/ansible-role-current-user)

# Ansible Role: marvel-nccr.current_user

An ansible role that stores information about the current ansible (become) user.

Correctly populates the variables:

    current_user:  # username of current become user
    current_user_home:  # home directory of current become user

## Installation

`ansible-galaxy install marvel-nccr.current_user`.

## Role Variables

See `defaults/main.yml`

## Example Playbook

```
  - hosts: servers
    roles:
    - role: marvel-nccr.current_user
```

## License

MIT

## Contact

Please direct inquiries regarding Quantum Mobile and associated ansible roles to the [AiiDA mailinglist](http://www.aiida.net/mailing-list/).
