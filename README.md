# Ansible

This monorepo contains some useful Ansible-playbooks.

__Ansible__ is an open-source automation tool that simplifies provisioning, configuration management and application deployment. 
It uses a declarative language to describe system configurations and orchestrates tasks across multiple systems.

In this repository, you can find several useful Ansible playbooks.

## Usage

_**Note**: You need to specify the addresses of the required hosts in inventory.yml_


To get started, clone this repository:

```shell
git clone https://github.com/issvvv/ansible.git && cd ansible/
```

Place your SSH key in the _~/.ssh/ssh-ansible_:

```shell
mv /path/to/your/ssh-ansible ~/.ssh/ssh-ansible
```

Navigate to the playbook directory and do what you need!
For example, run the minikube installation on your host:

```shell
ansible-playbook ./playbooks/deploy_minikube.yml
```

Enjoy! ✨