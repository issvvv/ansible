![Ansible Lint](https://github.com/issvvv/ansible/actions/workflows/ansible-lint.yml/badge.svg)

# Redis Ansible Playbook

This playbook automates the installation, configuration and management of Redis servers.

## 🤔 Features

- 🔄 **Multiple deployment options**
    - Standalone Redis server
    - Redis Cluster for data sharding
    - Redis Sentinel for high availability
- 🔐 **Security configuration**
    - Dedicated service user
    - Password protection
    - Firewall rules management
    - Protected mode settings
- ⚙️ **Operational benefits**
    - Logrotate
    - Systemd
    - Healthchecks

## 🏃‍♂️‍➡️ How to run?

As usual, clone this repository:

```shell
git clone https://github.com/issvvv/ansible.git && cd ansible/
```

Place your SSH key in the *~/.ssh/ssh-ansible* *(or somewhere else and configure ansible.cfg)*:

```shell
mv /path/to/your/ssh-ansible ~/.ssh/ssh-ansible
```

Start the process:

```shell
ansible-playbook playbooks/redis.yaml -e "host_group=redis"
```

 ## 🔧 Configuration

 Edit `inventory/group_vars/redis.yaml` to customize deployment parameters:

 ```yaml
# Redis version
redis_server_version: "7.4.5"

# Redis installation type: cluster — sharded Redis cluster; standalone — single-node server.
redis_server_instance_type: "cluster"

# Sentinel for high availability
redis_server_sentinel_enabled: true

# Password protection
redis_server_password: ""
 ```

You can specify any scenarios, like clusterized Redis or single-node Redis with Sentinel _(why do you need that?..)_. 

By the way, it works! 😊

## 🙏 Help me!

If you're really smart guy and see something wrong, please create an issue or submit a PR.
