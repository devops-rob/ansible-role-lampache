[![Build Status](https://travis-ci.org/robertraybarnes/ansible-role-lampache.svg?branch=master)](https://travis-ci.org/robertraybarnes/ansible-role-lampache)

Lampache
=========

Installs Apache, MariaDB and Python to Create a LAMP stack on CentOS and Ubuntu linux servers

Requirements
------------

None

Role Variables
--------------

```yaml
# Role variables for epel mirrors and MariaDB repository for centos

mariadb_url: http://yum.mariadb.org/10.1/centos7-amd64
epel_url: https://mirrors.fedoraproject.org/metalink?repo=epel-7&arch=$basearch

# Roles defaults are specific to the supported distributions respectively

packages:
  base:
    - "wget"
    - "nano"
    - "net-tools"
    - "unzip"
    - "zip"
    - "ntp"
    - "firewalld"
  lamp:
    - "httpd"
    - "mariadb-server"
  ubuntu:
    - "apache2"
    - "mariadb-server"
  python:
    - "python"
    - "gcc"
    - "python-pip"
    - "python-psutil"
    - "python-devel"
    - "MySQL-python.x86_64"
    - "mysql-connector-python"
  python_ubuntu:
    - "python"
    - "python3"
    - "python-dev"
    - "python-pymysql"
    - "python-pip"
    - "gcc"
    - "python-psutil"
firewall:
  services:
    - "http"
    - "https"
  ports:
    - "3306/tcp"
system_services:
  - "httpd"
  - "ntpd"
  - "firewalld"
  - "mariadb"
ubuntu_services:
  - "apache2"
  - "mysql"
```

Dependencies
------------

None

Example Playbook
----------------

```yaml
    - hosts: servers
      roles:
         - devopsrob.lampache
           become: yes
```

License
-------

BSD / MIT

Author Information
------------------

Robert Barnes (DevOpsRob)
