A simple virtual machine to test the Siesta ansible role and other bits.
Useful for the school.

You need to install virtualbox, vagrant and ansible.

Minimal steps (wip):

```
   ansible-galaxy install -r requirements.yml
```

Then:
```
  vagrant up
  vagrant provision
  vagrant ssh     # to connect to the VM
```

Provisioning is done according to the contents of the Vagrantfile. The file `playbook.yml` directs what to install in the VM.

- To halt, type `vagrant halt`.
- To bring up without provisioning: `vagrant up --no-provision`

## Installed bits

### OS

The base operating system comes from a pre-built vagrant box.

Since this is a no-desktop VM, for testing of graphical apps we need to add x11 client support. See
[this](https://fabianlee.org/2018/10/14/ubuntu-x11-forwarding-to-view-gui-applications-running-on-server-hosts/) for some background.

Install the x11 apps (xeyes et al) to test

```
sudo apt-get install x11-apps    # for things like xeyes...  xterm might not be included
sudo apt-get install xauth       # might be required also
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

The conda framework is installed using an experimental Marvel role.

Interested students can then install siesta-4.1.5 and the other packages using conda.
The hands-on material should probably be downloaded using 'git clone' against Nick's repo.

