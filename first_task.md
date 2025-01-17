# Первое самостоятельное задание с пары

1. apt-get install samba  
apt-get install bind  
apt-get install bind-utils (Автоматически установилось вместе с bind)  
apt-get install python3 arrows
2. 2.1) rpm -qi samba | grep Version  
2.2) rpm -ql samba   
2.3) apt-cache rdepends samba  
apt-cache rdepends --installed samba  
apt-cache depends samba  
apt-cache whatdepends --installed samba  
3. systemctl status smb  
systemctl start smb  
systemctl enable smb  
3.1) systemctl enable --now smb  
4. rpm -ql samba | grep ".service"
