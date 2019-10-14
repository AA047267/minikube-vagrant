Vagrant.configure("2") do |config|
  config.vm.box = "bento/centos-7.5"
  config.vm.network "private_network", type: "dhcp"
  config.vm.synced_folder "/", "/mnt"
  config.vm.host_name = 'vagrant'
  config.vm.provider "virtualbox" do |vb|
    vb.name = "FirstVM"
    vb.memory = "3072"
    vb.cpus = "2"
  end
  config.vm.provision "ansible_local" do |ansible|
    ansible.playbook = "ansible/playbook.yml"
    ansible.verbose = "-vvv"
    ansible.inventory_path = "ansible/inventory"
    ansible.extra_vars = {
      hostname: "localhost"
    }
  end
end
