# Ansible Playbooks

This repository contains several Ansible playbooks to automate various system administration tasks on Linux servers. These playbooks handle package updates, Nginx installation with custom HTML, static content deployment, and system reboots based on whether updates require them.

## Prerequisites

1. Install [Ansible](https://docs.ansible.com/ansible/latest/installation_guide/index.html) on your control node.
2. Ensure SSH access is available to the target Linux machines.
3. Configure the inventory file (`hosts`) with the correct IP addresses, usernames, and passwords for your environment.

## Inventory Configuration

Below is an example of the inventory file (`hosts`):

```ini
[linux]
192.168.1.4
192.168.1.5
192.168.1.6
192.168.1.7
192.168.1.8

[linux:vars]
ansible_user=ansible
ansible_password=AnsibleUser!
ansible_become_method=sudo
ansible_become=yes
```

## Commands
### Ping all hosts
This command ensures that Ansible can reach all target systems with the module (-m) ping:
```bash
ansible -i <inventory_file.yml> -m ping all
```
### Run a playbook
To execute a playbook on all specified hosts via inventory file:
```bash
ansible-playbook -i <inventory_file.yml> <playbook.yml>
```

To execute a playbook on all specified hosts via inventory file with asking ssh password (-k) and asking sudo password (-K):
```bash
ansible-playbook -i <inventory_file.yml> <playbook.yml> -kK
```

## Sources

* [Ansible - Ansible Documentation](https://docs.ansible.com/ansible/latest/installation_guide/index.html)
* [Medium - Ansible and Nginx Installation](https://medium.com/@JleeCloudEngineer/how-to-install-nginx-using-ansible-playbook-on-ubuntu-vm-to-display-custom-html-page-fe8e7be4b1bc)
* [Cyberciti - Apt Update with Ansible](https://www.cyberciti.biz/faq/ansible-apt-update-all-packages-on-ubuntu-debian-linux/)
* [Youtube - Ansible Playbooks Guide](https://www.youtube.com/watch?v=sSHpixS6OSo&list=PLXHMZDvOn5sW-EXm2Ur5TroSatW-t0Vz_&index=3)
* [ChatGPT for README](chatgpt.com)

##
© 2024 Julian Loontjens 