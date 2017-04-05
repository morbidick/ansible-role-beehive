VAGRANTFILE_API_VERSION = "2"

Vagrant.configure(VAGRANTFILE_API_VERSION) do |config|

  config.vm.box = "ubuntu/xenial64"

  config.vm.provision :ansible do |ansible|
    ansible.sudo = true
    ansible.playbook = "tests/role.yml"
  end

end
