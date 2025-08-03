![Ansible Lint](https://github.com/issvvv/ansible/actions/workflows/ansible-lint.yml/badge.svg)
[![Redis Docs](https://img.shields.io/badge/Redis-Docs-red?logo=redis)](https://redis.io/documentation/)

```text
                XXXXX                                                                  
           XXXXX;+++xXXXXX                                          Xx  XxX             
      XXXXXXXXx;;; :;xXXXXXXXXX                                    Xxx  XxX            
  XXXXXx.     .+XXxXXXXXX$$$$XXXXX                                 XxX                 
  XXXXXXXX+;+XXXXXXx+XXXXXXXXXXXXX      XxXXxXx  XXXXXxXx    XxXXxXXxX  XXX  XXxXXXX   
  XXXXXXXXXXXXx:.  +XXXXXXXXXXXXX       xXxxXXXxxXXX  XXxX XXxxXXXXxXx  XxX xxXx  xXX  
  XXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXX      xXXX   XXXxXxxXxxXXxxX     XXx  XxX XxxXXxX    
  XXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXX      Xxxx   XxXXXXXXXXxXXxX     XxX  XxX  XXxxXXxX  
  XXXXXXXXXXXXXXXXXXXXXXXXXXXXXXX       XxXX   XxxX        XxxX   XxxX  XxX xX    XxX  
  XXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXX      XxX     XXxxXxxxX   XXxxXxXXXX  xXX XxxXXxxXX  
  XXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXX       X         xXXX        XXXxxX   xXX    XXX     
   XXXXXXXXXXXXXXXXXXXXXXXXXXXXX                                                       
       $XXXXXXXXXXXXXXXXXXX$                                                           
            XXXXXXXXXXX                                                                
                XXX                                                                    
```

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

# standalone — single-node server; replication — HA Redis with replication; cluster — sharded Redis cluster
redis_server_instance_type: "replication"

# You need it only if redis_server_instance_type is set to 'replication'
redis_server_sentinel_enabled: true

# Password protection
redis_server_password: ""
 ```

## 📋 Deployment examples

1. Basic Redis Server (Standalone)
```yaml
redis_server_instance_type: "standalone"
redis_server_sentinel_enabled: false
```

2. Basic Replication (Master + Replicas)
```yaml
redis_server_instance_type: "replication"
redis_server_sentinel_enabled: false
```

3. High-Availability Redis (Master + Replicas + Sentinel)
```yaml
redis_server_instance_type: "replication"
redis_server_sentinel_enabled: true
```

4. Redis Cluster (Sharded Data)
```yaml
redis_server_instance_type: "cluster"
redis_server_sentinel_enabled: false
```

## ⚠️ Important Notes

Redis Cluster Initialization (I'll do it later in code)
After running the playbook with `redis_server_instance_type: "cluster"`, you need to manually initialize the cluster:

```shell
# Run this on just one of the cluster nodes
redis-cli --cluster create ip1:6379 ip2:6379 ip3:6379 --cluster-replicas 1
```

## 🙏 Help me!

If you're really smart guy and see something wrong, please create an issue or submit a PR.
