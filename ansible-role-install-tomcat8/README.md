ansible-role-install-tomcat8
============================

This role is to be played second as part of the ansible-playbook-clojure playbook. This specific role will deploy install apache tomcat version 8 on your host.

Requirements
------------

For this role to be played, the host must first have java installed on a host with CentOs or RHEL distribution of Linux .

Role Variables
--------------

This role have the below variables that can be set, depending on what version of tomcat you are installing and where you would like the installation directory to be located:

- tomcat_installation_directory:
- tomcat_binary_url:
- unarchived_tomcat_binary_folder:


Dependencies
------------

This role depends on the following roles being played on the host:

- ansible-role-install-java8

Example Playbook
----------------

The below can be added to your playbook.yml for example, which specifies what roles should played, in which order they should be played, what vars files should be parsed for your roles to consume and which hosts these roles should be played on. Where the env extra var specifies the host or group of hosts the ansible-controller should target.

    - hosts: "{{ env }}"
      vars_files:
         - ./vars/vars.yml
      roles:
         - ../ansible-role-install-tomcat8

 The role can then be played as:

     ansible-playbook [-i /path/to/hosts/file ] playbook.yml -e env=[centos] -b --ask-sudo-pass [--tags tomcat ]

License
-------

BSD

Author Information
------------------

The author of this role is m-abrarali (github account)
