# ansible-bigtop-zookeeper

an ansible role to install and configure zookeeper-server on rhel/centos 7

## sample playbook
```yml
- hosts: all
  remote_user: vagrant

  roles:
    - role: ansible-bigtop-zookeeper
      zookeeper_hosts: "{{groups['master']}}"
      when: '"master" in group_names'
```
