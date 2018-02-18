# ANSIBLE ROLE FOR APACHE-ACTIVEMQ

## SUPPORTED PLATFORMS
> Ubuntu-14.04

> Ubuntu-16.04

## VARAIABLES DEFINED IN ROLE

**amq_install_mode:** ""

> Enter the install mode 
> Two options:
> 1. 'apt' - To install amq by apt method
> 2. 'tarball' - To install amq by tarball method

**amq_user:** ubuntu

> ENTER THE USERNAME TO INTSALL AMQ

**amq_group:** ubuntu

> ENTER THE GROUP NAME TO INSTALL THE AMQ

**amq_port:** 8161

> ENTER THE UI PORT TO RUN AMQ

**amq_install_dir:** /opt

> ENTER THE INSTALLATION DIRECTORY

**amq_home_dir:** "{{ amq_install_dir }}/apache-activemq-{{ amq_version }}"

> ACTIVE-MQ HOME DIRECTORY

**amq_url_prefix:** "http://archive.apache.org/dist/activemq"

**amq_version_major:** "5"

**amq_version_minor:** "13"

**amq_version_patch:** "4"

> Enter exact version to install

**amq_version:** "{{ amq_version_major }}.{{ amq_version_minor }}.{{ amq_version_patch }}"

**amq_url:** "{{ amq_url_prefix }}/{{ amq_version }}/apache-activemq-{{ amq_version }}-bin.tar.gz"

**amq_service:** "yes"

> If you want amq as service give 'yes' else 'no'

## SAMPLE TEST.YML FILE

```
---
- name: Active-MQ installation
  hosts: activemq
  remote_user: ubuntu
  become: yes
  become_method: sudo
  vars:
    - amq_install_mode: "tarball"
    - amq_user: ubuntu
    - amq_group: ubuntu
    - amq_port: 8161
  roles:
    - bb-java
    - bb-activemq
    
```

## SAMPLE HOSTS FILE

```
[activemq]

ip/hostname
```
