Playbook Name
=============

This playbook comprises or 3 roles to ensure your host has java and apache tomcat installed and the clojure collector deployed.

Requirements
------------

For this role to be played, the host must be of a CentOs or RHEL Linux distribution.

Playbook Variables
------------------

This playbook comprises of 3 roles, the variables of which can be found in the individual role readme.md files.

Dependencies
------------

-

Example Playbook
----------------

The below can be added to your playbook.yml for example, which specifies what roles should played, in which order they should be played, what vars files should be parsed for your roles to consume and which hosts these roles should be played on. Where the env extra var specifies the host or group of hosts the ansible-controller should target.

    - hosts: "{{ env }}"
      vars_files:
         - ./vars/vars.yml
      roles:
         - ../ansible-role-deploy-clojure-collector

The role can then be played as:

     `ansible-playbook [-i /path/to/hosts/file ] playbook.yml -e env=[centos] -b --ask-sudo-pass --tags [java,tomcat,clojure]`

License
-------

BSD

Author Information
------------------

The author of this role is m.abrarali (github account)
