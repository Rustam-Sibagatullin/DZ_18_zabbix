# -*- mode: ruby -*-
# vim: set ft=ruby :




MACHINES = {
  :zabbixserever => {
#       :box_name => "centos/7",
#       :ip_addr => '192.168.11.101'
        :box_name => "centos/7",
        :ip_addr => '192.168.11.101'
 },

  :zabbixagent => {
        :box_name => "centos/7",
        :ip_addr => '192.168.11.102'
 }
}



Vagrant.configure("2") do |config|

  MACHINES.each do |boxname, boxconfig|

#    config.vm.provision "shell", path: "scriptful"
#     config.vm.provision "file", source: "default.conf", destination: "/etc/nginx/conf.d/default.conf"
#    config.vm.provision "shell", path: "script1"

      config.vm.define boxname do |box|

          box.vm.box = boxconfig[:box_name]
          box.vm.host_name = boxname.to_s
          box.vm.network "private_network", ip: boxconfig[:ip_addr]

          box.vm.provider :virtualbox do |vb|
            vb.customize ["modifyvm", :id, "--memory", "256"]
          end
      box.vm.provision "shell", inline: <<-SHELL
	      mkdir -p ~root/.ssh
          cp ~vagrant/.ssh/auth* ~root/.ssh
  	  SHELL

       end
    end
end	
