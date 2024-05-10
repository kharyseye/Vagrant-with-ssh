
Vagrant.configure("2") do |config|
  
  config.vm.define "server-panel" do |controlpanel|

    controlpanel.vm.box = "ubuntu/trusty64"

    controlpanel.vm.box_check_update = false

    #dbserver.vm.network "forwarded_port", guest: 8080, host: 8082

    controlpanel.vm.network "private_network", type: "static", ip: "192.168.0.10"

    #dbserver.vm.synced_folder "./mysqldata", "/var/lib/mysql/"

    controlpanel.vm.provider "virtualbox" do |vb|

      vb.gui = false
      vb.name = "control-panel"
      vb.memory = "1024"
      vb.cpus = 1
    end
  end

  config.vm.define "server-node" do |node1|

    node1.vm.box = "bento/ubuntu-22.04"

    node1.vm.box_check_update = false

    node1.vm.network "forwarded_port", guest: 8080, host: 8083

    node1.vm.network "private_network", type: "static", ip: "192.168.0.11"

    node1.vm.synced_folder "./node1", "/opt/"

    node1.vm.provider "virtualbox" do |vb|

      vb.gui = false
      vb.name = "node1"
      vb.memory = "1024"
    end
  end
end
