# On managing dotfiles

I have been looking for a way to manage my dotfiles. There are many options to do so:
- [stow](https://github.com/aspiers/stow)
- [chezmoi](https://github.com/twpayne/chezmoi)
- ~~[roost](https://github.com/mt-22/roost/tree/main)~~
    - Too new. Likely vibe coded slop

It's essentially "configurations-as-code" sort of deal.

## What about secrets?

There are things you must __never__ commit to public (or private) git repositories, including but not limited to:
- Credentials
- Private ssh keys

Each "dotfile management" solution has a different ways of handling this sort of thing. Consider selecting a password manager / secrets management solution and sticking to it such as `bw` (bitwarden CLI) or 1Password.

WIP

## Setting up and using `chezmoi`

Install `chezmoi`

```
sudo dnf install chezmoi -y
```

WIP

## Setting up and using `stow`

Install `stow`

```
sudo dnf install stow -y
```

WIP

## Tips and Tricks
- For stuff like `roost` where you have to build the package manually or there are no packages available in the official Fedora repos, you can use `distrobox` to get the package. This is especially helpful in cases where you are applying the dotfiles to an atomic flavor or bootc image.