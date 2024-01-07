# -*- mode: ruby -*-
# vi: set ft=ruby :
Vagrant.configure("2") do |config|
  config.vm.box = "bento/ubuntu-20.04"

# Install Postgresql-8.4 on VirtualBox via vagrant

   config.vm.provision "shell", inline: <<-SHELL
# Update packages
     sudo apt update -y
# Install curl ca-certificates gnupg
     sudo apt install -y wget mc
# Add Postgresql-8.4 repo
	 sudo sh -c 'echo "deb http://apt.postgresql.org/pub/repos/apt $(lsb_release -cs)-pgdg main" > /etc/apt/sources.list.d/pgdg.list'
#ADD key for repo
         sudo wget --quiet -O - https://www.postgresql.org/media/keys/ACCC4CF8.asc | sudo apt-key add -
# Update packages again
	 sudo apt update -y
# Install postgresql-8.4
	 sudo apt install -y postgresql-8.4 postgresql-client-8.4
# Enable postgresql.service
	 sudo systemctl enable --now postgresql.service
# Start service
         sudo systemctl start postgresql.service
  SHELL
end
