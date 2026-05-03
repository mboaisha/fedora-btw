# On packaging and package maintenance

> == **Work-In-Progress** ==


## Useful commands
- `rpm`: For when you want to interact with local packages
    - `rpm -q <package name>`: Query package files or installed packages
    - `rpm -qi <package name>`: Detailed information of a package. It shows you the content of the `.spec` file for the package.
    - `rpm -ql <package name>`: Tells you what files came with the package
      - Sometimes, you will want to query *uninstalled* pacakges, i.e. you have `xyz.rpm` and you want to view it's content: `rpm -qlp *.rpm`
    - `rpm -q --requires <package name>`: What packages on your system depend on `<package name>`?
    - `rpm --eval <macro>`: Evaluates macro expressions like `%{_libdir}` which should produce: `/usr/lib64`
- `dnf`: When you want to interact with repos
    - `dnf info <package name>`: View the spec file for a certain package. Detailed.
    - `dnf repoquery -l <package name>`: List the content of a package in the repos
    - `dnf repoquery --whatrequires <package name>`: "What packages in the repos depend on `<package name>`?
- `rpmspec`
    - `rpmspec -P <filename>.spec`: Parse (display) how the spec file would appear if queried.

## Tools Of The Trade
There are some helpful packages you might want to install when you do packaging:
- `bat`: `cat`, but better. Syntax highlighting!
    - `sudo dnf install bat`
- `git`: Might as well install `git` while we are at it. You will use it to retrieve sources to package and such.
    - `sudo dnf install git`
- `rpmbuild`:
    - `sudo dnf install rpmbuild`
- `rpmlint`:
    - `sudo dnf install rpmlint`
- `rpmdevtools`:
    - `sudo dnf install rpmdevtools`
- `rpmautospec`:
    - `sudo dnf install rpmautospec`
- `fedora-packager`: A set of tools to assist in the packaging process
    - `sudo dnf install fedora-packager`
- `rpmspectool`: Tool that helps with dealing with RPM spec files
    - `sudo dnf install rpmspectool`
- `spectool`: 

`podman` is helpful too, you can spin up a minimal Fedora container if you need to test things, explore COPRs, etc.

## Refernces and further reading

- [YouTube | Fedora Project: RPM Packaging classroom](https://www.youtube.com/watch?v=woFtdIS6x0Q)
    - `man dnf`
    - `man man`
    - `man hier`
- [Fedora Project Docs | Packaging Turorial](https://docs.fedoraproject.org/en-US/package-maintainers/Packaging_Tutorial/0)
- [YouTube | Fedora Project: Packaging for Beginners](https://www.youtube.com/watch?v=aLf4b03PHxM)
    - Long... format is not suitable for everyone.
- [Fedora Project Docs | RPM Macros](https://docs.fedoraproject.org/en-US/packaging-guidelines/RPMMacros/)
- [The DNF Team Blog | Spec file format](https://rpm-software-management.github.io/rpm/manual/spec.html)
    - *Extremely dry*, probably better used as a reference to keep on hand.
- [The DNF Team Blog | Macros](https://rpm-software-management.github.io/rpm/man/rpm-macros.7)
    - Also dry... it's about macros.
- [Red Hat Blog | How to create a Linux RPM package](https://www.redhat.com/en/blog/create-rpm-package)
    - I found it helpful. Might be dated.
- [Fedora Project Docs | Installing Packager Tools](https://docs.fedoraproject.org/en-US/package-maintainers/Installing_Packager_Tools/)
