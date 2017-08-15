### Install base packages

	sudo apt-get install pure-ftpd screen vim fail2ban

### Setup static ip

Add this to `/etc/dhcpcd.conf`:
	
	interface eth0
	static ip_address=192.168.1.122/24
	static routers=192.168.1.1
	static domain_name_servers=192.168.1.1
