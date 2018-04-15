# Configure environment

.clone:
	@clear
	@echo ""
	@rm -rf ansible
	@git clone --depth=1 https://github.com/maxwayne-mills/ansible.git

.clean:
	@echo ""
	@rm -rf config-managment .vagrant

.destroy-existing:
	@echo ""
	@vagrant destroy --force
	@rm *.log

all: .clone
	@echo ""
	@echo "Creating ansible configuration file"
	@./create_configs.sh
	@echo ""
	@echo "Provision server with Ansible"
	@echo ""
	@vagrant up --provision

clean: .clean

resync: .clone

provision:
	@echo ""
	@vagrant provision

status:
	@echo ""
	vagrant status

destroy: .destroy-existing
	
clone: .clone
