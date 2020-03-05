
Vagrant.configure("2") do |config|

  config.vm.box = "ubuntu/xenial64"
  config.vm.define "app" do |app|
    app.vm.network "private_network", ip: "192.168.15.30"
    app.vm.synced_folder "./node-sample-app-master", "/home/ubuntu/app"
    app.vm.provision "shell", path: "provision-app.sh"
  end

  config.vm.define "zap" do |zap|
    zap.vm.network "private_network", ip: "192.168.8.16"
    zap.vm.provision "shell", path: "provision-zap.sh"
  end

end
