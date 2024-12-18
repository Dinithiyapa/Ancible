# Docker Installation Ansible Role

This Ansible role installs Docker CE (Community Edition) on an Ubuntu system using the official Docker APT repository. It includes tasks to add dependencies, Docker's GPG key, the APT repository, and ensures Docker is installed and running.

## Requirements

- Ansible 2.x or higher
- Ubuntu 20.04 or later (for compatibility with Docker CE)

## Role Tasks

The role performs the following tasks:

1. **Install Docker dependencies**: Installs required packages such as `apt-transport-https`, `ca-certificates`, `curl`, `gnupg`, and `lsb-release`.
2. **Add Docker’s official GPG key**: Adds Docker’s GPG key for APT package verification.
3. **Add Docker APT repository**: Configures the official Docker APT repository for Ubuntu (Jammy version).
4. **Install Docker CE**: Installs Docker Community Edition (docker-ce).
5. **Ensure Docker service is running**: Starts the Docker service and ensures it is enabled to start on boot.

## Usage

To use this role, you need to include it in your Ansible playbook. Here is an example:

```yaml
---
- name: Install Docker on Ubuntu
  hosts: all
  become: yes
  roles:
    - docker

