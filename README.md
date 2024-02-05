# Ansible Role: Proxmox Container Management

This Ansible role automates the provisioning and management of containers on Proxmox VE using the Proxmox API.

## Role Variables

The role requires several variables to be defined, either in the playbook or in an inventory file:

*   `api_user`: The username for authenticating with the Proxmox API.
*   `api_password`: The password for authenticating with the Proxmox API.
*   `api_host`: The hostname or IP address of the Proxmox VE server.
*   `password`: The root password for the container.
*   `node`: The Proxmox VE node where the container will be created.
*   `cores`: The number of CPU cores assigned to the container.
*   `onboot`: Whether the container should start automatically on boot (true/false).
*   `disk`: The disk size for the container (e.g., 10G).
*   `memory`: The amount of memory assigned to the container (e.g., 512M).
*   `hostname`: The hostname for the container.
*   `ostemplate`: The name of the OS template to use for the container.
*   `pool`: The storage pool where the container's disk will be located.
*   `netif`: The network interface configuration for the container.
*   `pubkey`: The public key to be added to the container for SSH access.
*   `swap`: The amount of swap space allocated to the container.
*   `features`: Additional features or options for the container creation.
*   `api_token_id`: (Optional) The API token ID for authentication (if using API token).
*   `api_token_secret`: (Optional) The API token secret for authentication (if using API token).
*   `lxc_container`: (Optional) Copy the LXC image from files. (if template is not present in Proxmox.)

## Example Playbook

```yaml
# site.yml
- hosts: proxmox_servers
  become: true
  roles:
    - proxmox_lxc 
  vars_files:
    - main.yml
```

Replace the variable values with your specific configuration.

## License

This role is licensed under the MIT License.
