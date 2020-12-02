A simple virtual machine to test the Siesta ansible role.

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
