# DZ_18_zabbix

Vagrantfile содержит 2 машины  

  :zabbixserever => {
        :box_name => "centos/7",
        :ip_addr => '192.168.11.101'
 },

  :zabbixagent => {
        :box_name => "centos/7",
        :ip_addr => '192.168.11.102'
 }

на одном разовравчивается сервер: zabbixserever, на другом агент zabbixagent.  

История устовка сервера и агента в файле 
Zabbix_install_commands_for_server_and_agent

  
скриншоты с настаройкой мониторинга в файле Zabbix_front_end.odt  
