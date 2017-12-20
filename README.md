# Ansible MacOS Playbook

This is the playbook I use after a clean install of MacOS to set everything up.

Advantages for me over using a shell script based setup

- I can run the playbook over and over again with the same results.
- Tasks are only executed when changes are needed.
- The documentation about what is done is right in the output,
  instead of only in the comments.
- When a task doesn't work anymore, for example after a new macOS release,
  I will know immediately which one and why.
- It helps me to improve my Ansible skills :)

My dotfiles are managed with [yadm](https://thelocehiliosan.github.io/yadm/)
and stored in a private git repository which is pulled in the first time
the playbook is run. The repository is private because it includes
sensitive data like private keys and GitHub tokens. This approach
allows me to only need the login data of the dotfiles repo
provider when setting up a computer from scratch.

## Installation

### Automated

```bash
sh -c "$(curl -fsSL https://raw.githubusercontent.com/jeromegamez/ansible-macos-playbook/master/install.sh)"
```

### Manual

```bash
# Install Apple's Command Line Tools
xcode-select --install

# Install Homebrew (see http://brew.sh)
/usr/bin/ruby -e "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install)"

# Install ansible
brew install ansible

# Clone this repository
https://github.com/jeromegamez/ansible-macos-playbook.git

# Run the playbook
ansible-playbook main.yml
```

### Variables

If you want to use this playbook for your own computer, fork the repository and
execute `cp vars/defaults.yml vars/${USER}.yml` - you can change any variable
in that file however you like.

## Acknowledgements

This playbook is heavily inspired by
[Jeff Geerling's mac-dev-playbook](https://github.com/geerlingguy/mac-dev-playbook).

The macOS settings (a.k.a. `defaults write`s) are mostly taken from
[Mathias Bynens' defaults scripts](https://mths.be/macos) or from one of the
dotfiles repos from [http://dotfiles.github.io](http://dotfiles.github.io).
