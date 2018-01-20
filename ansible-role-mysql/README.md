# ANSIBLE ROLE FOR MYSQL-SERVER

## SUPPORTED PLATFORMS

> Ubuntu-16.04
> Ubuntu-14.04

## VARIABLES DEFINED IN ROLE

**mysql_package_name:** mysql-server

> Enter the mysql-server package name to install 

**apt_cache_valid_time:** 600

> Enter apt-cache valid time ( not important )

**mysql_user_name:** bigbrain

> Specify the non-root username

**mysql_user_password:** bigbrain

> Password for non-root user

**mysql_admin_username:** devops

> Enter the name for root/admin user

**mysql_admin_password:** devops

> Enter the password for root/admin user 

**mysql_user_host:** '%'

> Enter host connection type % or localhost.

> The percent '%' symbol means: any host, including remote and local connections.

> The 'localhost' allows only local connections.

> OR you can give particular hostname (host1.example.com), or part of hostname(%.example.com)

**mysql_priv:** '\*.\*:ALL'

> Enter privileges for non-root user

> MySQL privileges string in the format: db.table:priv1,priv2

**mysql_remote_access:** 'yes'

> Type 'yes', if we require remote access.

**mysql_port:** 3306

> Specify mysql port

**mysql_data_dir:** /var/lib/mysql

> Specify data directory ( recommended to mount in different volume )

**mysql_bind_address:** '0.0.0.0'

> Specify the bind address, bind to all or specific group of host.If you dont want remote connection this value will be 'no'

## SAMPLE test.yml FILE
```
---
- hosts: namenode
  remote_user: ubuntu
  become: yes
  become_method: sudo
  vars:
    #PACKAGE SPECIFIC
    mysql_package_name: mysql-server
    apt_cache_valid_time: 600
    
    #ADMIN USER SPECIFIC
    mysql_admin_username: devops
    mysql_admin_password: devops

    #NON-ROOT USER SPECIFIC
    mysql_user_name: bigbrain
    mysql_user_password: bigbrain
    mysql_user_host: '%'
    mysql_priv: '*.*:ALL'
    
    #CONFIGURATION SPECIFIC
    mysql_remote_access: 'yes'
    mysql_port: 3306
    mysql_data_dir: /var/lib/mysql
    mysql_bind_address: '0.0.0.0'
  roles:
    - mysql-server
   ```
   
 ## SAMPLE HOST FILE
 ```
 [MYSQL]
 IP/HOSTNAME
 ```
