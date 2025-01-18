# Конфижим для удобства

1. Пользовательские конфигурации - ~/.ssh/config  
Системные - /etc/openssh/sshd_config  
2. Судя по следующим задачам, речь идёт о ~/.ssh/config  
Этот файл содержит алиасы SSH, чтобы не вводит постоянно все параметры доступа.
 
3-4) Подключаюсь я к своему 2 серверу alt linux  
nano /home/dlozereg/.ssh/config  

Host test  
     User student  
     HostName 192.168.1.72  
     Port 22 

5. ssh test  
