# Ansible Docker and Nginx Setup

This repository contains an Ansible playbook that installs Docker and Nginx on your server, configures Docker, and sets up Nginx with a custom `index.html` page.

## Prerequisites

Ensure that you have the following set up before running the playbook:

- Ansible installed on your local machine
- A remote server to run the playbook on (I used EC2 instance)
- SSH access to the server
- The `inventory.ini` file properly configured with your server's details

### Key Files and Their Roles

| File/Directory           | Description                                                                 |
|--------------------------|-----------------------------------------------------------------------------|
| **docker/tasks/main.yml** | Contains tasks to install Docker and ensure its service is running.         |
| **nginx/tasks/main.yml**  | Contains tasks to install Nginx, copy an `index.html` file to the web root, and ensure the Nginx service is running. |
| **inventory.ini**         | An inventory file defining the hosts to be configured.                     |
| **nginx_docker.yaml**     | The main playbook that runs both Docker and Nginx roles.                   |
| **files/index.html**      | The HTML file served by the Nginx web server.                              |


## How to Use

### Step 1: Update the Inventory File

Edit the `inventory.ini` file to specify your target hosts.

### Step 2: Place Your HTML File

Replace the `files/index.html` file with your custom HTML content to be served by Nginx.

### Step 3: Run the Playbook

Execute the playbook with the following command:

```bash
ansible-playbook -i inventory.ini nginx_docker.yaml
```

### Step 4: Verify the Setup

1. **Nginx**:
   - Open a web browser and navigate to the IP address of your target machine.
   - You should see the content of your custom `index.html` file.

2. **Docker**:
   - Verify that Docker is installed and running by logging into the target machine and running:
     ```bash
     docker --version

## Notes

- The Docker installation tasks in `docker/tasks/main.yml` use the official Docker APT repository to install Docker CE.
- The Nginx tasks ensure the web server is running and the `index.html` file is served with the correct permissions.

*Author: Dinithi Yapa*
