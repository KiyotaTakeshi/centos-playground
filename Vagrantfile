Vagrant.configure("2") do |config|
	config.vm.define 'centos-playground' do |main|
		# https://app.vagrantup.com/ubuntu/boxes/focal64/versions/20210811.0.0
		main.vm.box = "centos/7"
		main.vm.box_version = "2004.01"
		main.vm.hostname = "centos-playground"
	
		# https://www.vagrantup.com/docs/networking/private_network.html
		main.vm.network "private_network", ip: "192.168.33.15"
	
		main.vm.synced_folder "./data", "/vagrant"
	
		# https://www.vagrantup.com/docs/virtualbox/configuration.html#vboxmanage-customizations
		main.vm.provider "virtualbox" do |vb|
			vb.memory = "2048"
			vb.cpus = 2
		end

		# 2回目以降の起動時に provision を走らせたい場合
		# vagrant up --provision
		$script = <<-SCRIPT
		sudo yum update -y
		SCRIPT

		main.vm.provision "shell", inline: $script
	end
end