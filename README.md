# Ansible MacOS Playbook

This is the playbook I use after a clean install of MacOS to set everything up.

## Roles/Tasks

- Installs Homebrew packages and app casks (Role `homebrew`)
- Installs App Store apps with [`mas-cli`](https://github.com/mas-cli/mas) (Role `mas`)
- Modifies MacOS settings (Role `settings`)
- Changes the user shell, if configured (Role `shell`)

## Installation

1. Install [Homebrew](https://brew.sh).

```shell
brew install ansible
# Don't skip this, otherwise your computer will be provisioned like mine
cp default.config.yml config.yml
# Review the changes the playbook will apply
ansible-playbook --check main.yml
# Actually apply them
ansible-playbook main.yml
```

## Updating a fork with the latest changes from this repository

If you forked this repository and want to include its latest changes without losing your own,
add this repository as an upstream and rebase it onto your fork:

```bash
git remote add upstream git@github.com:jeromegamez/ansible-macos-playbook.git
git fetch upstream
git rebase upstream/main
```

## Acknowledgements

This playbook is heavily inspired by
[Jeff Geerling's mac-dev-playbook](https://github.com/geerlingguy/mac-dev-playbook).

The macOS settings (a.k.a. `defaults write`s) are mostly taken from
[Mathias Bynens' defaults scripts](https://mths.be/macos) or from one of the
dotfiles repos from [http://dotfiles.github.io](http://dotfiles.github.io).
