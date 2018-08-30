Vagrant.configure("2") do |config|

  (0..2).each do |containernumber|
    config.vm.define "container#{containernumber}" do |container|
      container.vm.hostname = "vault#{containernumber}"
      container.vm.network "forwarded_port", guest: 8200, host: "1822#{containernumber}"
      container.vm.network :private_network, ip: "192.168.13.3#{containernumber}"
      config.vm.provider "docker" do |d|
        d.image = "vault"
      end
    end
  end
end
