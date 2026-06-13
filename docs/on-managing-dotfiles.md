# On managing dotfiles

I have been looking for a way to manage my dotfiles. There are many options to do so:
- [stow](https://github.com/aspiers/stow)
- [chezmoi](https://github.com/twpayne/chezmoi)
- [roost](https://github.com/mt-22/roost/tree/main)

## What about secrets?

There are things you must __never__ commit to a public (or private) git repositories, including but not limited to:
- Credentials
- Private ssh keys

Each "dotfile management" solution has a different ways of handling this sort of thing. Consider selecting a password manager / secrets management solution and sticking to it such as `bw` (bitwarden CLI) or 1Password.

WIP

## Setting up and using `roost`
First, you must install the dependencies:

```
sudo dnf install git cargo -y
```

Then, install the package from crates.io:

```
cargo install roost-dot
```

WIP

## Setting up and using `stow`

WIP

## Setting up and using `chezmoi`

WIP