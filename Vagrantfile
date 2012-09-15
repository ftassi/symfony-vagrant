# http://vagrantup.com/v1/docs/vagrantfile.html

Vagrant::Config.run do |config|
  config.vm.box = "base"
  config.vm.box_url = "http://files.vagrantup.com/precise64.box"

  config.vm.network :hostonly, "33.33.33.10"
  config.vm.customize ["modifyvm", :id, "--memory", 1024]
  config.vm.share_folder "v-root", "/home/vagrant/code", ".", :nfs => true

  config.vm.provision :puppet do |puppet|
    puppet.manifests_path = "manifests"
    puppet.module_path = "modules"
    puppet.manifest_file  = "app.pp"
  end
end
