# Post-Installation Recommendations and Guide

> AKA, what I usually do after a fresh install

## Password change
- Anaconda, the OS installer always crashes for me when I put my usual password because it's "too weak"
- To fix that, I usually do `00<my password>00` to proceed in the installation process.
- After the first boot and first log-in, I simply do `sudo passwd mboaisha`
    - "Change password as `root` for user `mboaisha`"

**Note:** It's not recommended to do this, this is just a comfort / Quality-of-Life thing for me, especially if I am testing stuff in a VM. Always pick a strong password.

## Configure, start and enable `sshd`
- I like to be able to `ssh` into all my machines.
    - Why? Remote management, remoting into machines from far away places, etc
- Sometimes the `sshd` service is dead / disabled on fresh installs,as such, you will have to enable them.

First order of business is to check the status of the `sshd` service: `sudo systemctl status sshd.service`

```
# TODO: Output goes here

```

## `bootc` / Atomic Fedora specific stuff

If you are running an Atomic flavor of Fedora such as Fedora Silverblue and you had a successful installation with an operational OS, it's a good time (and idea) to [pin](https://docs.fedoraproject.org/en-US/atomic-desktops/updates-upgrades-rollbacks/#pinning-and-cleaning-deployments) the current image (Note: Fedora calls them *deployments*, I like to call them images.) before you do anything so you have a last stable image for you to rollback to.

First, you should check the status of your currently booted image: `sudo rpm-ostree status`

```
# TODO: output
```
