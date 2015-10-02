# AnsibleTest

This is a simple playbook to install git on my server (ubuntu server) and install virtual box onto my individual machine.

1) Clone this repo

2) nano SAVEDDIRECTORY/ansible-test/roles/virtualbox/tasks/main.yml

Firstly, according to your distribution, replace 'trusty' by 'utopic', 'vivid', 'raring', 'quantal', 'precise', 'lucid', 'jessie', 'wheezy', or 'squeeze'.
As I was using standard ubuntu, mine was 'trusty' as you can see below

apt_repository: repo='deb http://download.virtualbox.org/virtualbox/debian trusty contrib' state=present

3) Change directory to where you cloned it and hop into the new directory e.g. cd ~/ansible-test/
4) Run the command 'ansible-playbook -i inventory roles.yml -u root'

This should run through the installation of firstly GIT and then secondly, Virtual box.

