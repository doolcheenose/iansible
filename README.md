# Ansible automation for things in my home

## Setup

First install `uv`: <https://docs.astral.sh/uv/#installation>

Build and enter the Python environment with

    uv sync
    source .venv/bin/activate

## Run playbooks

Run a playbook with the `ansible-playbook` command (from the Python environment). For example:

    ansible-playbook \
        maintenance.yaml \        # which playbook to run
        --limit pi-zero-2w.local  # optionally limit to certain hosts or groups

### maintenance.yaml

- Runs `apt-get dist-upgrade` on all hosts.

### dev_env.yaml

- Installs development tools like neovim, tmux, git, GNU stow, etc.
- Clones my [dotfiles repo](https://github.com/doolcheenose/dotfiles) and sets up configuration for neovim and tmux.

### media_server.yaml

- Installs docker, terraform, and k3s.
- Clones my [homelab repo](https://github.com/doolcheenose/homelab).
- Does not actually do a `terraform apply`. Maybe something I'll add in the future.
