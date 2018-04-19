Vagrant.configure(2) do |config|
  config.vm.box = "ignatev/centos-7.2-docker"

  ssh_public_key = File.read(File.join(Dir.home, ".ssh", "id_rsa.pub"))

  config.vm.network "private_network", ip: "192.168.33.100"
  config.vm.network :forwarded_port, guest: 80, host: 80
  config.vm.provision "shell", inline: <<-SHELL
    sudo yum update
    echo "#{ssh_public_key}" >> /home/vagrant/.ssh/authorized_keys
  SHELL

  config.vm.provision :ansible do |ansible|
    ansible.playbook = "ansible-docker-nginx.yml"
    ansible.verbose = "v"
  end
end
