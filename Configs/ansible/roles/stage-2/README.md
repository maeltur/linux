STAGE-2
=========

The purpose of this role is to deploy a ready-to-use apache web server

Requirements
------------

All needed packages should be installed by the role. 

The only requirements is having ssh access to the host. You can check it with ansible -m ping  host

Role Variables
--------------

All variables are stored in the vars folder of the role in file named after the hostname. 

For example : for apache2.projet.intranet you can find apache2.projet.intranet.yml with the following content :

```yaml
---
#list of vars by host
ports:
  - '80'
  - '443'
  - '8080'
vhosts:
  - name: http
    port: '80'
    direct_name: '/var/www/site'
    log_folder: '/var/log/apache/site'
    log_type: 'combined'
  - name: https
    port: '443'
    direct_name: '/var/www/site-https'
    log_folder: '/var/log/apache/https'
    log_type: 'combined'
  - name: test
    port: '8080'
    direct_name: '/var/www/site-test'
    log_folder: '/var/log/apache/test'
    log_type: 'combined'
```



Example Playbook
----------------

Including an example of how to use your role (for instance, with variables passed in as parameters) is always nice for users too:

```yaml
---
- name: install pakcages and deploy ssh
  hosts: web
  become: yes
  become_method: sudo
  roles:
    - stage-2
```
