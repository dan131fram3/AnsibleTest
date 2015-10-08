#AnsibleTest

This is a simple playbook to install Virtualbox onto my individual machine.

1) Clone this repo

2) nano SAVEDDIRECTORY/ansible-test/roles/virtualbox/tasks/main.yml

Firstly, according to your distribution, replace 'trusty' by 'utopic', 'vivid', 'raring', 'quantal', 'precise', 'lucid', 'jessie', 'wheezy', or 'squeeze'. As I was using standard ubuntu, mine was 'trusty' as you can see below

apt_repository: repo='deb http://download.virtualbox.org/virtualbox/debian trusty contrib' state=present

3) Change the 'inventory' contents to your chosen machines ip addresses

4) Change directory to where you cloned it and hop into the new directory e.g. cd ~/ansible-test/ 

5) Run the command 'ansible-playbook -i inventory roles.yml -u root'

This should run through the installation of Virtualbox.
