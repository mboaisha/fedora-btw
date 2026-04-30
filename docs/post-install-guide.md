# Post-Installation Recommendations and Guide

> AKA, what I usually do after a fresh install

## Password change
- Anaconda, the OS installer always crashes for me when I put my usual password because it's "too weak"
- To fix that, I usually do `00<my password>00` to proceed in the installation process.
- After the first boot and first log-in, I simply do `sudo passwd mboaisha`
    - "Change password as `root` for user `mboaisha`"

**Note:** It's not recommended to do this, this is just a comfort / Quality-of-Life thing for me, especially if I am testing stuff in a VM. Always pick a strong password.

## Install, configure, start, and enable `sshd`
- I like to be able to `ssh` into all my machines.
    - Why? Remote management, remoting into machines from far away places, etc
- Sometimes the `sshd` service is dead / disabled on fresh installs,as such, you will have to enable them.

First order of business is to check the status of the `sshd` service: `sudo systemctl status sshd.service`

```
[root@fedora-tester ~]# systemctl status sshd
Unit sshd.service could not be found.
```

There are cases where you won't even have an `ssh` daemon running, in this case, you can install it like so:

```
sudo dnf install -y sshd
```

Now let's try to see the status again...

```
[root@fedora-tester ~]# systemctl status sshd
○ sshd.service - OpenSSH server daemon
     Loaded: loaded (/usr/lib/systemd/system/sshd.service; enabled; preset: enabled)
    Drop-In: /usr/lib/systemd/system/service.d
             └─10-timeout-abort.conf
             /run/systemd/system/service.d
             └─zzz-lxc-service.conf
     Active: inactive (dead)
       Docs: man:sshd(8)
             man:sshd_config(5)
```

It appears `sshd` (The ssh daemon) is running. In my case, it appears that upon installing the packakges, the `systemd` units were taken care of. To manually start and enable the service, you will have to do this:

```
systemctl enable --now sshd
```

This command should start and enable the service, meaning, you will have the `sshd` started automatically upon booting.

From here, you can connect to your machine via `ssh`, you will just have to figure out the IP address: `ip addr show`

## `bootc` / Atomic Fedora specific stuff

If you are running an Atomic flavor of Fedora such as Fedora Silverblue and you had a successful installation with an operational OS, it's a good time (and idea) to [pin](https://docs.fedoraproject.org/en-US/atomic-desktops/updates-upgrades-rollbacks/#pinning-and-cleaning-deployments) the current image (Note: Fedora calls them *deployments*, I like to call them images.) before you do anything so you have a last stable image for you to rollback to.

First, you should check the status of your currently booted image: `sudo rpm-ostree status`

```
# TODO: output
```
