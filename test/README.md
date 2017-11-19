# Vagrant 2.x

Vagrant 2.x installs python 3.x, this will cause Ansible to fail, to get around this install python 2.x prior to running your ansible plays.

### Configure Vagrant to use Ansible
```
Vagrant.require_version ">=2.0.0"
Vagrant.configure("2") do |config|
  config.vm.box = "ubuntu/xenial64"
  config.vm.provision "shell", path: "setup.sh"
  config.vm.provision "ansible" do |ansible|
    ansible.verbose = "-v"
    ansible.config_file = "/home/cmills/Documents/repositories/ansible/ansible.cfg"
    ansible.playbook = "/home/cmills/Documents/repositories/ansible/roles/users/users.yml"
    ansible.limit = "all"
  end
end
```
**ansible.cfg** file
```
[defaults]
retry_files_enabled = False
host_key_checking = False
roles_path = /home/cmills/Documents/repositories/ansible/roles
#inventory = inventory
```
The inventory section is commented out to allow vagrant to use the automated inventory file generate by vagrant within the .vagrant directory
