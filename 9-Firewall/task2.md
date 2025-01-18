# Открываем firewald

1. iptables -F  
systemctl stop iptables  
apt-get install firewalld  
systemctl status firewalld.service  
systemctl start firewalld.service  
2. ssh test (алиас)  
Подключение произошло.

3-4) firewall-cmd --list-ports  
5) Да.  
firewall-cmd --add-service=servicename  
6-7) Подключиться удалось.  
8) firewall-cmd --runtime-to-permanent  

