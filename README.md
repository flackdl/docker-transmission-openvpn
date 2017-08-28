### Install packages

	# change default password
	passwd
	
	# install base packages
	sudo apt-get install -y pure-ftpd screen vim fail2ban apt-transport-https
	
	# docker
	curl -sSL https://get.docker.com | sudo sh
	sudo usermod -aG docker pi
	
	# docker compose
	sudo apt-get install -y apt-transport-https
	echo "deb https://packagecloud.io/Hypriot/Schatzkiste/debian/ jessie main" | sudo tee /etc/apt/sources.list.d/hypriot.list
	sudo apt-key adv --keyserver keyserver.ubuntu.com --recv-keys 37BBEE3F7AD95B3F
	sudo apt-get update
	sudo apt-get install -y docker-compose
	
### Configure

	# generate ssh keys (add to publicly accessible server for reverse ssh)
	ssh-keygen
	# copy to this directory and secure permissions
	cp ~/.ssh/id_rsa .
	chmod 600 id_rsa
		
	
### Setup static ip

Add to `/etc/dhcpcd.conf`:
	
	interface eth0
	static ip_address=192.168.1.222/24
	static routers=192.168.1.1
	static domain_name_servers=192.168.1.1

### Clone this repository

    git clone https://github.com/flackdl/rpi-consumer.git
    cd rpi-consumer/
    # get submodules
    git submodule update --recursive
    # copy and edit .env
    cp .env.example .env
