Role Name
=========

An Ansible role that installs LXD on Ubuntu and performs base configuration as given in get started guide

Requirements
------------

- The host to which this role is being deployed must be Ubuntu

Role Variables
--------------

| Variable | Description | Default Value | Possible Values |
|----------|-------------|---------------|-----------------|
|lxd_allow_remote|Allow operations from remote lxc clients using https api|false|true|false|
|lxd_https_listen_address|bind address for the api|[::]|lxd API bind address|
|lxd_trust_password|turst password to be used by remote lxc clients|4trustlxd123|string|
|lxd_lxc_path|path to installed lxc binary after lxd installation|/usr/bin/lxc|do not modify this unless installation path is modified by installer|


Dependencies
------------

None

Example Playbook
----------------

Install lxd

    # example1.yml
    # example playbook to install lxd

    - hosts: lxd0
      roles:
	- { role: thebinary.lxd }


Install lxd and configure it to allow operations using remote lxc client

    # example2.yml
    # example2 playbook to install lxd and configure it for remote operations

    - hosts: lxd1
      roles:
         - { role: thebinary.lxd, lxd_allow_remote: true }


    - hosts: lxd2
      roles:
         - { role: thebinary.lxd, lxd_allow_remote: true, lxd_trust_password: "somepassword" }

License
-------

MIT

Author Information
------------------

thebinary <binary4bytes@gmail.com>
