# Настриваем

1. Порт по умолчанию - 22.  
2. Да, можно.  
nano /etc/openssh/sshd_config  
Строку "# Port 22" нужно раскоментировать и поменять цифры.  
service sshd reload   
3. За это отвечает служба sshd.  
4. /etc/openssh/sshd_config  
5. Я подключался к своему второму alt linux серверу  
ssh student@192.168.1.72 -p 22
6. control sshd-permit-root-login enabled  
systemctl restart sshd  
7. nano /etc/openssh/sshd_config  
Изменить строку MaxAuthTries 6  
8. useradd -m ssh-user  
passwd ssh-user  
ssh ssh-user@192.168.1.72 -p 22
 
9-10) nano /etc/openssh/sshd_config  
DenyUsers ssh-user  
11) В known_hosts хранится список известных ключей серверов. 
