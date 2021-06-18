[![CI](https://github.com/marvel-nccr/ansible-role-siesta/workflows/CI/badge.svg)](https://github.com/marvel-nccr/ansible-role-siesta/actions)
[![Ansible Role](https://img.shields.io/ansible/role/25521.svg)](https://galaxy.ansible.com/marvel-nccr/siesta)
[![Release](https://img.shields.io/github/tag/marvel-nccr/ansible-role-siesta.svg)](https://github.com/marvel-nccr/ansible-role-siesta/releases)

# Ansible Role: marvel-nccr.siesta

An Ansible role that installs [Siesta](https://gitlab.com/siesta-project/siesta) on Ubuntu.

It can install any MaX-1.X version. These are 'preview' versions with
important features (PSML, etc), not yet merged into the master
version. 

PSML support is important to access databases and prepare
pseudopotentials for all elements, as needed by the aiida-siesta
package, which supports PSML since the 1.1.0 version. Fuller support
for protocols, also heavily dependent on the PSML feature, appeared in
the 1.1.1 version. Older versions of aiida-siesta can also work with
this version of Siesta, although they will not be able to access all
the features.

Note that support for the ELSI library (the other major feature of the
rel-MaX-1 branch) is not compiled in for deployments in the QuantumMobile,
as it is mostly a performance feature.

With minor changes detailed in the defaults/main.yml file, this role can also
compile the 4.1-rc2 version of Siesta, in the beta branch.

Future versions along the rel-MaX-1 and rel-4.1 branches could in
principle be built, as long as they can still use the same libraries,
and as long as they have a proper tag in the Gitlab repository.


## Installation

`ansible-galaxy install marvel-nccr.siesta`

## Role Variables

See `defaults/main.yml`.

In particular, `siesta_version` can be set to the desired tag. By default,
it is set to `MaX-1.2.0`.

This role uses the marvel-nccr.libxc role to install versions of libxc
in those systems where libxc package support is sub-standard. The required
libxc version can be set through the variable `siesta_libxc_version`, which
is `4.3.4` by default.

## Example Playbook

```yaml
- hosts: servers
  roles:
  - role: marvel-nccr.siesta
    vars:
      siesta_version: "MaX-1.2.0"  # tag in GitLab
```

## Development and testing

This role uses [Molecule](https://molecule.readthedocs.io/en/latest/#) and [Docker](https://www.docker.com/) for tests.

After installing [Docker](https://www.docker.com/):

Clone the repository into a package named `marvel-nccr.siesta` (the folder must be named the same as the Ansible Galaxy name)

```bash
git clone https://github.com/marvel-nccr/ansible-role-siesta marvel-nccr.siesta
cd marvel-nccr.siesta
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
