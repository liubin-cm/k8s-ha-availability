Ansible Role: kubernetes-high-availability
========================

Install kubernetes master 1.2.6 on CentOS 7 servers. 

Requirements
------------

Written in Ansible 2.0.*

Role Variables
--------------

Available variables are listed below, I define it in /etc/ansible/hosts, for example:
```
[k8-master]
10.47.0.1 etcd_name=etcd160
10.47.0.2 etcd_name=etcd164
10.47.0.3 etcd_name=etcd165

[k8-master:vars]
etcd_init=etcd160=http://10.47.0.1:2380,etcd164=http://10.47.0.2:2380,etcd165=http://10.47.0.3:2380
```
variable etcd_name should be contained in etcd_init.

Dependencies
------------

- python2.7
- supervisord, you can use https://github.com/liubin-cm/ansible-role-supervisor install supervisord on centos 7 

Example Playbook
----------------

    - hosts: servers
      roles:
        - liubin.k8s-ansible

License
-------

MIT
