
# Шарим


1. apt-get install samba  
2. Общая папка - папка, доступ к которой имеют пользователи в локальной сети. Такую папку удобно иметь, если необходимо часто перекидывать информацию с одного пк в локальной сети на другой.  
3. mkdir sharedfold  
chown 666 sharedfold  
cp /etc/samba/smb.conf /etc/samba.conf.old  
nano /etc/samba/smb.conf  

В конфиге:  
[global]  
dos charset = CP866  
unix charset = utf8  
workgroup = WORKGROUP  
server string = Files  
security = USER  
map to guest = Bad User  

[PublicFiles]  
path = /var/sharedfold  
guest ok = Yes  
browseable = yes  
writable = no  
read only = yes  
create mask = 0666  
directory mask = 0666  
4. useradd -m share  
passwd share  
mkdir /var/passfold  
chmod 666 /var/passfold  
chown -R share:users /var/passfold  
chmod -R ugo+rwx /var/passfold  
smbpasswd -a share  
nano /etc/samba/smb.conf  

В конфиге:  
[Paroled]  
        path = /var/passfold  
	read only = no  
	guest ok = no  
	browseable= yes  
	writable=yes  
        create mask = 0666  
        directory mask = 0666  
	force user = share  
        force group = users  

systemctl restart smb.service nmb.service  
5. mkdir /var/onlysome  
chmod 666 /var/onlysome
nano /etc/samba/smb.conf  

В конфиге:  
[Onlysome]  
    path = /var/onlysome  
    public = no  
    writable = no  
    read only = yes  
    guest ok = no  
    valid users = @dlozereg  
    write list = @dlozereg  
    create mask = 0775  
    directory mask = 0775  
    force create mode = 0775  
    force directory mode = 0775  
    inherit owner = yes  


systemctl restart smb.service nmb.service  
6.mkdir /var/specific  
chmod 666 /var/specific
nano /etc/samba/smb.conf  

В конфиге:  
[Specific]  
    path = /var/specific  
    public = no  
    writable = no  
    read only = yes  
    guest ok = no  
    valid users = @dlozereg, @myuser  
    write list = @dlozereg, @myuser  
    create mask = 0775  
    directory mask = 0775  
    force create mode = 0775  
    force directory mode = 0775  
    inherit owner = yes  


systemctl restart smb.service nmb.service  
 
