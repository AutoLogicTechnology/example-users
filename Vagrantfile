
VAGRANTFILE_API_VERSION = "2"

Vagrant.configure(VAGRANTFILE_API_VERSION) do |config|
  config.vm.box = "movedx/centos-6.6"
  config.vm.network :private_network, ip: "10.0.2.15"

  config.vm.provision :ansible do |ansible|
    ansible.playbook = "site.yml"
    ansible.inventory_path = "site.inventory"
  end

  config.vm.define "db-01" do |box|
    box.vm.network :forwarded_port, guest: 22, host: 5000
  end

  config.vm.define "web-01" do |box|
    box.vm.network :forwarded_port, guest: 22, host: 5001
  end
  
end
