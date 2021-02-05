STAGE-2
=========

The purpose of this role is to deploy a ready-to-use apache web server

Requirements
------------

All needed packages should be installed by the role. 

The only requirements is having ssh access to the host. You can check it with ansible -m ping  host

Role Variables
--------------

A description of the settable variables for this role should go here, including any variables that are in defaults/main.yml, vars/main.yml, and any variables that can/should be set via parameters to the role. Any variables that are read from other roles and/or the global scope (ie. hostvars, group vars, etc.) should be mentioned here as well.

Example Playbook
----------------

Including an example of how to use your role (for instance, with variables passed in as parameters) is always nice for users too:

    ---
    - name: install pakcages and deploy ssh
      hosts: apache2.projet.intranet
      become: yes
      become_method: sudo
      
      vars:
        ports:
          - '80'
          - '443'
          - '8080'
        direct_name: '/var/www/site'
        log_folder: '/var/log/apache/test'
        log_type: 'combined'
        
      roles:
        - stage-2

License
-------

BSD

Author Information
------------------

An optional section for the role authors to include contact information, or a website (HTML is not allowed).
