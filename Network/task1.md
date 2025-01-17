
# сети

1. 1.1) ip -br link show  
1.2) nmcli device status  
1.3) netstat -i  
2. ip addr show - узнать имя адаптера (enp0s3)  
ip link set enp0s3 down  
echo 10.0.2.64/24 > /etc/net/ifaces/enp0s3/ipv4address  
echo default via 10.0.2.64 > /etc/net/ifaces/enp0s3/ipv4route  
nano /etc/net/ifaces/enp0s3/options  
Изменения параметра BOOTPROTO=static  
service network restart  
3. echo 10.0.2.65/24 >> /etc/net/ifaces/enp0s3/ipv4address  
echo default via 10.0.2.65 >> /etc/net/ifaces/enp0s3/ipv4route  
4. route  
5. arp -a  
6. IP-адресс - это уникальный числовой идентификатор устройства в компьютерной сети.  
7. Маршруты нужны для определения пути, по которомы должны пойти пакеты, чтобы достичь адресата.  
8. Arp - протокол, необходимый для определения соответствия между IP и MAC.  
9. DHCP - протокол, автоматически раздающий IP-адреса и другие параметры конфигурации устройствам сети.  
10. DNS - система, которая позволяет браузеру найти запрошенный пользователем сайт по имени домена.  
11. Протокол NTP  
12.  Широковещательный запрос - запрос, который посылается сразу нескольким участникам сети.  
13. 255.255.255.255  
14. TYPE, NM_CONTROLLED, DISABLED, CONFIG_WIRELESS, SYSTEMD_BOOTPROTO, CONFIG_IPV4, SYSTEMD_CONTROLLED, ONBOOT, CONFIG_IPV6.  
15. Маска подсети - 32-битное число, позволяющее удобно выделять из IP-адреса номер сети и номер хоста.
