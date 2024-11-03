# minecraft-bedrock-patch

This repository contains a patch playbook for Minecraft Bedrock servers. The playbook is designed to automate the process of upgrading Minecraft Bedrock servers.

# Overview
The playbook is written in Ansible and consists of several tasks that perform the following actions:

* Upgrade the Minecraft Bedrock server to the specified version
* Backup the existing Minecraft directory
* Download and install the new version of Minecraft Bedrock
* Configure the new version of Minecraft Bedrock

## Requirements
* Ansible 2.9 or later
* Minecraft Bedrock server installed on the target machine
* SSH access to the target machine

## Configuration
The playbook uses several variables that can be configured in the inventory/secrets.yaml file:

`ansible_user`: The username to use for SSH connections
`ansible_ssh_password`: The password to use for SSH connections
`ansible_become_password`: The password to use for privilege escalation
`ansible_ssh_private_key_file`: The path to the private key file to use for SSH connections
`mc_bedrock_version`: The version of Minecraft Bedrock to install
`mc_dir`: The directory where Minecraft Bedrock is installed

## Usage
To run the playbook, navigate to the repository root and execute the following command:

```
ansible-playbook -i inventory/inventory.yaml patch.yaml
```

OR

```
ansible-navigator run -m stdout patch.yaml --eei apigban-ee:latest -i inventory/inventory.yaml
```

## Notes
The playbook assumes that the Minecraft Bedrock server is installed in the /var/lib/pufferpanel/servers/7f3aca4a directory. If your installation is in a different directory, you will need to modify the mc_dir variable in the patch.yaml file.

The playbook uses the ansible-vault tool to store sensitive data, such as passwords and private keys. If you need to modify these values, you will need to use the ansible-vault tool to decrypt and re-encrypt the files.