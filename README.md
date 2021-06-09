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

## Installed bits

### OS

The base operating system comes from a pre-built vagrant box.

For testing of graphical apps we need to add x11 client support. See
[this](https://fabianlee.org/2018/10/14/ubuntu-x11-forwarding-to-view-gui-applications-running-on-server-hosts/) for some background.

Install a simple gui-based app to test, like:

```
sudo apt-get install vim-gtk     # sample app for testing
sudo apt-get install xauth       # might be required also
sudo apt-get install x11-apps    # for things like xterm and xeyes...
```

Then, make sure you put this in the Vagrantfile to be able to get back the X flow:

```
config.ssh.forward_agent = true
config.ssh.forward_x11 = true
```

### Siesta and school material

Siesta is installed with the Marvel role.
We include the libxc role to keep compatibility with what they do in the QMobile.

### TranSiesta school bits

This will involve packaging with ansible the instructions for download of material for the TS school.
