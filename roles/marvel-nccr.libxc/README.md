[![CI](https://github.com/marvel-nccr/ansible-role-libxc/workflows/CI/badge.svg)](https://github.com/marvel-nccr/ansible-role-libxc/actions)
[![Ansible Role](https://img.shields.io/ansible/role/25521.svg)](https://galaxy.ansible.com/marvel-nccr/libxc)
[![Release](https://img.shields.io/github/tag/marvel-nccr/ansible-role-libxc.svg)](https://github.com/marvel-nccr/ansible-role-libxc/releases)

# Ansible Role: marvel-nccr.libxc

An ansible role to install [libxc](gitlab.com/libxc/libxc).

See also: See: https://www.tddft.org/programs/libxc/installation/.

## Installation

`ansible-galaxy install marvel-nccr.libxc`

## Role Variables

See `defaults/main.yml`

## Example Playbook

```yaml
- hosts: servers
  roles:
  - role: marvel-nccr.libxc
    vars:
      libxc_version: "4.3.4"  # git release
```

## Development and testing

This role uses [Molecule](https://molecule.readthedocs.io/en/latest/#) and [Docker](https://www.docker.com/) for tests.

After installing [Docker](https://www.docker.com/):

Clone the repository into a package named `marvel-nccr.libxc` (the folder must be named the same as the Ansible Galaxy name)

```bash
git clone https://github.com/marvel-nccr/ansible-role-libxc marvel-nccr.libxc
cd marvel-nccr.libxc
```

Then run:

```bash
pip install -r requirements.txt  # Installs molecule
molecule test  # runs tests
```

or use tox (see `tox.ini`):

```bash
pip install tox
tox
```

## Code style

Code style is formatted and linted with [pre-commit](https://pre-commit.com/).

```bash
pip install pre-commit
pre-commit run -all
```

## Deployment

Deployment to Ansible Galaxy is automated *via* GitHub Actions.
Simply tag a release `vX.Y.Z` to initiate the CI and release workflow.
Note, the release will only complete if the CI tests pass.

## License

MIT

## Contact

Please direct inquiries regarding Quantum Mobile and associated ansible roles to the [AiiDA mailinglist](http://www.aiida.net/mailing-list/).
