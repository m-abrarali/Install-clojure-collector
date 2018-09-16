# Install-clojure-collector
Install clojure collector via cloudformation and ansible.

# HOW TO PROVISION THE INFRASTRUCTURE

Please go the cloudformation console in AWS and select Design template. Here upload the clojure-infra.template file.

The standard Linux ami was chosen for this which is based on CentOs distribution of Linux.

Once happy go ahead and click create stack.

This will create a multi-az, load balanced and auto scaled tomcat web server with clojure. The collector is configured to span all availability zones in the region and is auto-scaled based on the CPU utilisation of the web servers. Notifications will be sent to the operator email address on scaling events.

# HOW TO CONFIGURE INFRASTRUCTURE

Once cloudformation has completed creating the stack, obtain the ssh key pair and ensure your ansible controller (your laptop) has this public key installed.
The default user to log-in with this key will be the ec2-user. You can ssh in with this user to set up your user/authorized keys etc.
Lastly add the host ip to your inventory file and run the playbook.

The zip file contains all you need to get you going, 3 roles which the playbook runs, once unzipped into the same folder, cd in the ansible-playbook-clojure directory and run:


          ansible-playbook playbook.yml -e env=host(s) -b --ask-sudo-pass


Please refer to the individual README.md files located in each role and playbook for more detailed information on the configuration of the server.

Any changes that are made should be reflected in the CHANGELOG.md files, using semantic versioning and the latest change should be on top.

