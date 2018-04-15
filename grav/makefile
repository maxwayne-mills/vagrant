# Configure environment

.clone:
	rm -rf ansible
	git clone --depth=1 https://github.com/maxwayne-mills/ansible.git

.clean:
	rm -rf config-managment .vagrant

.destroy-existing:
	vagrant destroy --force

all: .clone
	vagrant up --provision

clean: .clean

resync: .clone

provision:
	vagrant provision

status:
	vagrant status

destroy: .destroy-existing
	
clone: .clone
