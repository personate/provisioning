Vagrant.configure(2) do |config|

  config.vm.define :dev do |dev|
    dev.vm.box = "ubuntu/trusty64"
    dev.vm.network :private_network, ip: "10.123.2.222"
    dev.vm.hostname = "dev-personite"

    dev.vm.provision :ansible do |ansible|
      ansible.inventory_path = "./inventories/dev-vagrant"
      ansible.playbook = "foundation/dev.yml"
      ansible.limit = ["dev-vagrant"]
      # "v", "vv", "vvv", "vvvv". 4 x v for the most verbose debugging info
      ansible.verbose = "vvvv"
    end
  end

end
