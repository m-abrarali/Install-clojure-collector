ansible-role-deploy-clojure-collector
=========

This role is to be played third as part of the ansible-playbook-clojure playbook. This specific role will deploy the clojure collector WAR file to your tomcat server.

Requirements
------------

For this role to be played, the host must first have java and tomcat webserver configured.

Role Variables
--------------

This role have the below variables that can be set, depending on what version of the WAR file you are deploying and where you would like the file to be downloaded, also where your tomcat installation directory is located:
- tomcat_installation_directory
- clojure_collector
- clojure_destination_folder

Dependencies
------------

This role depends on the following roles being played on the host:

- ansible-role-install-java8
- ansible-role-install-tomcat8

Example Playbook
----------------

The below can be added to your playbook.yml for example, which specifies what roles should played, in which order they should be played, what vars files should be parsed for your roles to consume and which hosts these roles should be played on. Where the env extra var specifies the host or group of hosts the ansible-controller should target.

    - hosts: "{{ env }}"
      vars_files:
         - ./vars/vars.yml
      roles:
         - ../ansible-role-deploy-clojure-collector

The role can then be played as:

     `ansible-playbook [-i /path/to/hosts/file ] playbook.yml -e env=[centos] -b --ask-sudo-pass [--tags clojure ]`

License
-------

BSD

Author Information
------------------

The author of this role is m.abrarali (github account)
