Ansible Role Nginx Site
======================================

Ansible role to configure sites for nginx service.

Requirements
------------

None.

Role Variables
--------------

- `nginx_user`:
Name of system user to run service with. Default value is "nginx"

- `nginx_group`:
Name of system group to run service with. Default value is "nginx"

- `nginx_services`:
Array with services to be restarted on configuration changes. Default value
is ["nginx"]

- `nginx_sites`:
Array with site configuration. Also called server blocks. See
[default vars file](defaults/main.yml)

Dependencies
------------

None.

Example Playbook
----------------
```
- hosts: all
  roles:
    - role: vundb-nginx-site
      nginx_sites:
        - label: "example.com"
          listen_hosts: ["80"]
          server_names: ["example.com"]
          access_log: "/var/log/nginx/example.com.access_log"
          error_log:  "/var/log/nginx/example.com.error_log"
          root: "/var/www/example.com"
```

License
-------

MIT

Author Information
------------------

- You can find more roles in my GitHub channel [vundb](https://github.com/vundb)
- Follow me on Twitter [@vundb](https://twitter.com/vundb)
