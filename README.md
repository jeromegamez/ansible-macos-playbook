# Mac Bootstrap Ansible Playbook

This is the playbook I use after a clean install of MacOS to set everything up.
It also pulls in a private [yadm](https://thelocehiliosan.github.io/yadm/)
dotfiles repository.

## Installation

1. Clone this repository
2. Install Apple's Command Line Tools (`xcode-select --install`)
3. Install [Homebrew](http://brew.sh)
4. Install Ansible (`brew install ansible`)
5. Run `ansible-playbook main.yml`

or automated

1. Clone this repository
2. Run `bash install.sh`
