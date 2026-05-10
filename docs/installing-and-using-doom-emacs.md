# Installing and using Doom Emacs

Came across this some time ago... Thought I'd give it a shot.

# Notes
Emacs has this convention:
- `M` is alt, 
- `S` is shift and
- `s` is super


# Getting set up

## Non-Atomic Fedora

The guide in [the Doom Emacs repo](https://github.com/doomemacs/doomemacs/blob/master/docs/getting_started.org) is quite straightforward.

First, you must install the dependencies for `doom` and actually get `emacs`:
```
# required dependencies
sudo dnf install emacs git ripgrep
# optional dependencies
sudo dnf install fd-find    # is 'fd' in Fedora <28
```

At this point, you should be able to install Doom Emacs:

```
git clone --depth 1 https://github.com/doomemacs/doomemacs ~/.config/emacs
~/.config/emacs/bin/doom install
```

It's also a good idea to add `doom` to your $PATH also, that is, adding this snippet in your `~/.bashrc`

```
export PATH="$HOME/.emacs.d/bin:$PATH"
```

After adding the snippet, you will have to either source your `.bashrc` (like so: `source ~/.bashrc`) or re-login to be able to use the `doom` command or `emacs` with the `doom` goodies.

`doom doctor` should tell you if everything is working properly. For me, I had to do couple of things:
- `M-x nerd-icons-install-fonts`: Execute this inside Doom Emacs
- `sudo dnf install gdouros-symbola-fonts`: `doom doctor` complained about not having the `symbola` theme. This is how you'd install it in Fedora (44)

I also had two warnings:
```
  > Checking your enabled modules...
    > :lang markdown
      ! Couldn't find a markdown compiler, `markdown-preview' won't work
    > :lang sh
      ! Couldn't find shellcheck. Shell script linting will not work
```

To resolve them, you will have to install the `shellcheck` and `marked` packages.

- `sudo dnf install -y shellcheck`
- `sudo dnf install -y marked`

At this point, you should get something like this:

```
mboaisha@fedora44-buildbox:~$ doom doctor
The doctor will see you now...

> Checking your Emacs version...
> Checking for Doom's prerequisites...
> Checking for Emacs config conflicts...
> Checking for missing Emacs features...
> Checking for fonts...
> Checking for private config conflicts...
> Checking for common environmental issues...
> Checking for stale elc files...
> Checking for problematic git global settings...
> Checking Doom Emacs...
  ✓ Initialized Doom Emacs 2.1.0
  ✓ Detected 33 modules
  ✓ Detected 109 packages
  > Checking Doom core for irregularities...
    Found Symbols Nerd Font Mono
  > Checking for stale elc files in your DOOMDIR...
  > Checking your enabled modules...

Everything seems fine, happy Emacs'ing!
```
## Atomic Fedora
In some cases, you may have either [Toolbx / Toolbox](https://github.com/containers/toolbox) or [Distrobox](https://docs.bazzite.gg/Installing_and_Managing_Software/Distrobox/)

For Distrobox, the first step is to create the container:

```
distrobox create doomEmacs
```

And then, you enter it:

```
distrobox enter
```

From here, you can follow the non-Atomic Fedora installation guide. If youare having any issues, check if you have the dependency packages already e.g. Already have `emacs` from Homebrew

# Using Doom Emacs

    TODO

# References
- [GitHub | doomemacs/doomemacs: Getting Started, Fedora](https://github.com/doomemacs/doomemacs/blob/master/docs/getting_started.org#fedora)

# TODOs
- Add notes on how'd you install in an atomic Fedora
    - Probably would need to use `brew`
    - Maybe there is an easier / alternative way
    - ~~Maybe through `toolbox` / `distrobox` also~~
    - I suppose layering stuff is also an option...
