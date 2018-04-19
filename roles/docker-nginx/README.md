Role Name
=========

This role install  nginx on  docker alpine images

Requirements
------------


Role Variables
--------------
all the varaibles are intialized with defaults in defaults/main.yml


Dependencies
------------



Example Playbook
----------------

- hosts: all
  roles:
    - role: docker-nginx
      nginx_files_local_folder: './files/nginx'
      nginx_configuration_files: ['default.conf']

License
-------

BSD

Author Information
------------------

Satish Gummadelli
