Ansible Playbooks and Roles
===========================
Roles
=====
- ``common``: Applied to all servers, installs and configure common things
- ``web``: Applied to web servers, installs and configure nginx+ssl
- ``application``: Applied to application servers, installs and configure php5+wordpress
- ``database``: Applied to database servers, installs and configure mariadb

Virtual machine specifications
==============================
Web Server
----------
- ``Image``: CentOS
- ``Storage``: Ephemeral (Nova)
- ``Network``: LAN+WAN

``Misc``:

- Security group on port 80, 443, 2222
- Nginx with SSL termination
- Let's encrypt SSL certificate
- Scale horizontally by adding application servers (templated nginx upstream)

Application Server
------------------
- ``Image``: Fedora
- ``Storage``: Ephemeral (OS), Persistent (Data)
- ``Network``: LAN

``Misc``:

- php5+wordpress

Database Server
---------------
- ``Image``: CentOS
- ``Storage``: Persistent (OS+Data)
- ``Network``: LAN

``Misc``:

- MariaDB
