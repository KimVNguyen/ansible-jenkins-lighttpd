# ansible-jenkins-lighttpd

Uses vagrant's ansible provisioner to provision a VM with Jenkins to build lighttpd.

## Getting started

### Prequsites

- Vagrant Installed
- Virtual Installed
- Ansible Installed

### VM Specifics
- Operating System: Centos 7
- Port 8080 mapped from host to guest os to use Jenkins Web interface
- Job "lighttpd" is run on initial provisioning of VM

### To Run
Open a terminal and run:

	vagrant up

once the vagrant up process has started, from your host machine you can browse to http://localhost:8080 and you will see the lighttpd job with a build task.

## To Do
- Add make install command to build job - need to find a way to gain root access from Jenkins
- create restart handler for Jenkins - currently the restart command is handled as a task.  Ideally the restart function should be a handler and called as a notification from the task preceding the current calls to restart Jenkins.
- Add system to wait for the build of lighttpd to finish.  Currently the Ansible playbook's usage of the Jenkins CLI does not have any logic to wait until the build job is completed.