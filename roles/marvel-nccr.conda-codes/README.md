[![CI](https://github.com/marvel-nccr/ansible-role-conda-codes/workflows/CI/badge.svg)](https://github.com/marvel-nccr/ansible-role-conda-codes/actions)
[![Ansible Role](https://img.shields.io/ansible/role/25521.svg)](https://galaxy.ansible.com/marvel-nccr/conda-codes)
[![Release](https://img.shields.io/github/tag/marvel-nccr/ansible-role-conda-codes.svg)](https://github.com/marvel-nccr/ansible-role-conda-codes/releases)

# Ansible Role: marvel-nccr.conda-codes

An Ansible role that installs computational codes from Conda

## Codes

| Code | Recipe | MPI |
| ---- | ------ | --- |
| abinit | [![recipe][abinit-badge]][abinit-link] | mpich |
| cp2k | [![recipe][cp2k-badge]][cp2k-link] | openmpi |


[abinit-badge]: https://img.shields.io/badge/recipe-abinit-green.svg
[abinit-link]: https://github.com/conda-forge/abinit-feedstock
[cp2k-badge]: https://img.shields.io/badge/recipe-cp2k-green.svg
[cp2k-link]: https://github.com/conda-forge/cp2k-feedstock


## Installation

`ansible-galaxy install marvel-nccr.conda-codes`

## Role Variables

See `defaults/main.yml`

## Example Playbook

```yaml
- hosts: servers
  roles:
  - role: marvel-nccr.conda-codes
```

## Development and testing

This role uses [Molecule](https://molecule.readthedocs.io/en/latest/#) and [Docker](https://www.docker.com/) for tests.

After installing [Docker](https://www.docker.com/):

Clone the repository into a package named `marvel-nccr.conda-codes` (the folder must be named the same as the Ansible Galaxy name)

```bash
git clone https://github.com/marvel-nccr/ansible-role-conda-codes marvel-nccr.conda-codes
cd marvel-nccr.conda-codes
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


## Development Notes

TODO: change version of package in existing env
