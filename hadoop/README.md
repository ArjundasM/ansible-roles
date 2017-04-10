ANSIBLE HADOOP ROLE FOR AWS INSTANCES
=====================================
1. Sample hosts file 
[datanode]
x.x.x.x
y.y.y.y

[namenode]
x.y.x.y

[newdatanode]

[hadoop:children]
datanode
namenode

2. Sample main yml file

---
- name: Hadoop cluster installation
  gather_facts: yes
  hosts: hadoop,newdatanode
  remote_user: ubuntu
  become: yes
  become_method: sudo
  roles:
    - java-8
    - hadoop
