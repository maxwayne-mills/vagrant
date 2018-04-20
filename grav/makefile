# Configure environment

.clone:
	@clear
	@echo ""
	@rm -rf ansible
	@git clone --depth=1 https://github.com/maxwayne-mills/ansible.git
	@echo ""
	@rm -rf shell_scripts
	@git clone --depth=1 https://github.com/maxwayne-mills/shell_scripts.git

.clean:
	@echo ""
	@rm -rf config-managment .vagrant


.destroy-existing:
	@echo ""
	@vagrant destroy --force
	@rm *.log ansible.cfg
	@rm -rf ansible shell_scripts

all: .clone
	@echo ""
	@echo "Creating ansible configuration file"
	@shell_scripts/ansible_config_setup.sh
	@echo ""
	@echo "Provision server with Ansible"
	@echo ""
	@vagrant up --provision

clean: .clean

resync: .clone

provision:
	@echo ""
	make clone
	@vagrant provision

status:
	@echo ""
	vagrant status

destroy: .destroy-existing
	
clone: .clone

up:
	@vagrant up

redo:
	@make destroy && make

