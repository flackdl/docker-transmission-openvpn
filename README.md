### Setup

	# change default password
	passwd
	
	# install base packages
	sudo apt-get install pure-ftpd screen vim fail2ban
	
	# docker
	curl -sSL https://get.docker.com | sudo sh
	sudo usermod -aG docker pi
	
	# docker compose
	sudo apt-get install -y apt-transport-https
	echo "deb https://packagecloud.io/Hypriot/Schatzkiste/debian/ jessie main" | sudo tee /etc/apt/sources.list.d/hypriot.list
	sudo apt-key adv --keyserver keyserver.ubuntu.com --recv-keys 37BBEE3F7AD95B3F
	
	
### Setup static ip

Add this to `/etc/dhcpcd.conf`:
	
	interface eth0
	static ip_address=192.168.1.122/24
	static routers=192.168.1.1
	static domain_name_servers=192.168.1.1
