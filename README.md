# Mac Bootstrap Ansible Playbook

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
the playbook is run. The repository is private because they include
sensitive data like private keys and GitHub tokens. This approach
allows me to only need the login data of the dotfiles repo
provider when setting up a computer from scratch.

## Installation

1. Clone this repository
2. Install Apple's Command Line Tools (`xcode-select --install`)
3. Install [Homebrew](http://brew.sh)
4. Install Ansible (`brew install ansible`)
5. Run `ansible-playbook main.yml`

or automated

1. Clone this repository
2. Run `bash install.sh`

## Acknowledgements

This playbook is heavily inspired by
[Jeff Geerling's mac-dev-playbook](https://github.com/geerlingguy/mac-dev-playbook).

The macOS settings (a.k.a. `defaults write`s) are mostly taken from
[Mathias Bynens' defaults scripts](https://mths.be/macos) or from one of the
dotfiles repos from [http://dotfiles.github.io](http://dotfiles.github.io).
