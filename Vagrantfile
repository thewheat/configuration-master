Vagrant::Config.run do |config|
  config.vm.define :configuration_master do |configuration|
    configuration.vm.box = "centos57_86_64"
    configuration.vm.box_url = 'http://dl.dropbox.com/u/8072848/centos-5.7-x86_64.box'
    configuration.vm.customize [
      "modifyvm", :id,
      "--name", "configuration-master",
      "--memory", "1024"
    ]
    configuration.vm.host_name = "configuration-master"
    configuration.vm.forward_port 8153, 8153
    configuration.vm.share_folder ".", "/home/vagrant/configuration-master", "."
    configuration.vm.provision :shell, :path => "scripts/boot_script.erb"
  end
end