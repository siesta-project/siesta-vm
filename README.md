A simple virtual machine to test the Siesta ansible role and other bits.
Useful for the school.

You need to install virtualbox, vagrant and ansible.

Minimal steps (wip):

The first time, init the git submodules:

```
  git submodule --init update
```
Then:
```
  vagrant up
  vagrant provision
  vagrant ssh
```

Provisioning is done according to the contents of the Vagrantfile. The file `playbook.yml` directs what to install in the VM.

- To halt, type `vagrant halt`.
- To bring up without provisioning: `vagrant up --no-provision`

