
VAGRANTFILE_API_VERSION = "2"

Vagrant.configure(VAGRANTFILE_API_VERSION) do |config|
  config.vm.box = "movedx/centos-6.6"
  config.vm.provision :ansible do |ansible|
    ansible.playbook = "site.yml"
    ansible.groups = {
      "webservers" => ["web-01"],
      "databases" => ["db-01"],
      "git" => ["ci-01"],
    }
  end

  config.vm.define "web-01"
  config.vm.define "db-01"
  config.vm.define "ci-01"
end
