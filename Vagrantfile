VAGRANTFILE_API_VERSION = "2"

Vagrant.configure(VAGRANTFILE_API_VERSION) do |config|
  config.vm.box = "puphpet/debian75-x64"
  config.vm.network "forwarded_port", guest: 80, host: 12380
  config.vm.provider "virtualbox" do |vb|
     vb.name = "misp"
     vb.customize ["modifyvm", :id, "--memory", "512"]
  end

  config.vm.provision :ansible do |ansible|
    ansible.playbook = "misp.yaml"
  end
end
