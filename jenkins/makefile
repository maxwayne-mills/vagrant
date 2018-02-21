# Configure environment

.clone:
	git clone https://github.com/maxwayne-mills/config-managment.git

.clean:
	rm -rf config-managment .vagrant

.destroy-existing:
	vagrant destroy --force

all: .clone
	vagrant up --provision

clean: .clean

destroy: .destroy-existing
	
