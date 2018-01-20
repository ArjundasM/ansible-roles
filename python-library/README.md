# ROLE FOR INSTALLING PYTHON-LIBRARIES
This role will install required list of python3.5 libraries.

## PRE-REQUISTIES

> Python3.5

> Pip3.5

## SUPPORTED PLATFORMS

> Ubuntu-14.04

> Ubuntu-16.04

## VARIABLES IN ROLE
**python_packages:**

> Enter the required library names line by line like follows:
```
python_packages:
  - boto
  - pyhdfs
```
  
## EXAMPLE TEST.YML FILE

```
- name: Install python libraries
  hosts: python
  remote_user: ubuntu
  become: yes
  become_method: sudo
  gather_facts: true
  vars:
    python_packages:
      - boto
      - smartopen
      - pyhdfs
  roles:
    - python-library
```
