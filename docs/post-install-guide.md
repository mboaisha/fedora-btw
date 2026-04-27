# Post-Installation Recommendations and Guide

> AKA, what I usually do after a fresh install

## Password change
- Anaconda, the OS installer always crashes for me when I put my usual password because it's "too weak"
- To fix that, I usually do `00<my password>00` to proceed in the installation process.
- After the first boot and first log-in, I simply do `sudo passwd mboaisha`
    - "Change password as `root` for user `mboaisha`"

**Note:** It's not recommended to do this, this is just a comfort / Quality-of-Life thing for me, especially if I am testing stuff in a VM. Always pick a strong password.
