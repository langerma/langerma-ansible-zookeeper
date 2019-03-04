# langerma-ansible-zookeeper

an ansible role to install and configure zookeeper-server on rhel/centos 7

## sample playbook
```yml
- hosts: master
  become: true
  vars:
    java_version: 11
    java_install_dir: "/app/java"
    supervisord_ini_dir: "/app/supervisord.d"
    zookeeper_install_tar: "files/zookeeper-3.4.13.tar.gz"
    zookeeper_install_dir: "/app/zookeeper"

  roles:
    - role: langerma-ansible-zookeeper
      zookeeper_hosts: "{{groups['master']}}"
      when: '"master" in group_names'
```
