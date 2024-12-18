# Nginx Ansible Role

This Ansible role installs and configures Nginx on Ubuntu-based systems. It performs the following tasks:
- Installs Nginx.
- Copies a custom `index.html` file from the role’s `files` directory to the Nginx web root (`/var/www/html/index.html`).
- Ensures that the Nginx service is running and enabled to start on boot.

The `index.html` file is served through the Nginx web server, which can be accessed via the IP addresses of the servers specified in the `inventory.ini` file.

## Requirements

This role assumes the following:

- Ubuntu-based system (e.g., Ubuntu 20.04, 22.04, etc.)
- Ansible installed on the control machine
- The target system(s) should be accessible via SSH
- Ensure that the `inventory.ini` file is properly configured with the IP addresses of the servers you want to deploy Nginx on.

##  Playbook
Define the  role in the playbook

`
