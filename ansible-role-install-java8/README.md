Role Name
=========

This role is to be played first as part of the ansible-playbook-clojure playbook. This specific role will install java8 on your host.

Requirements
------------

For this role to be played, the host must be on a CentOs or RHEL distribution of Linux.

Role Variables
--------------

This role have the below variables that can be set, depending on what distribution of Linux your host is running. Future improvement could be to allow the roles to be played on other distributions such as Debian.

ansible_distribution:
  - CentOS

Dependencies
------------

This role depends on the host having a CentOs or RHEL distribution of Linux.

Example Playbook
----------------

The below can be added to your playbook.yml for example, which specifies what roles should played, in which order they should be played, what vars files should be parsed for your roles to consume and which hosts these roles should be played on. Where the env extra var specifies the host or group of hosts the ansible-controller should target.

    - hosts: "{{ env }}"
      vars_files:
         - ./vars/vars.yml
      roles:
         - ../ansible-role-install-java

The role can then be played as:

     `ansible-playbook [-i /path/to/hosts/file ] playbook.yml -e env=[centos] -b --ask-sudo-pass [--tags java ]`

License
-------

BSD

Author Information
------------------

The author of this role is m.abrarali (github account)
