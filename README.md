# Ansible

This repository contains some useful Ansible-playbooks.

__Ansible__ is an open-source automation tool that simplifies provisioning, configuration management, and application deployment. 
It uses a declarative language to describe system configurations and orchestrates tasks across multiple systems. 
Ansible is agentless, utilizing SSH for communication, making it easy to set up and use.

In this repository, you can find several useful Ansible playbooks.

## Usage

_**Note**: You need to specify the addresses of the required hosts in inventory.yml_


To get started, clone this repository:

'''shell
git clone https://link.ru/sex.git && cd ansible/
'''

Place your SSH key in the root of the Ansible repository:

'''shell
mv /path/to/your/ssh-ansible .
'''

Navigate to the playbook directory and do what you need!
For example, run the minikube installation on your host:

'''shell
ansible-playbook ./playbooks/minikube-installation.yml
'''

Enjoy! ✨