# Управление пользователями

1. 1.1) useradd -m -s /bin/bash user1  
1.2) useradd -m -s /bin/sh user2  
1.3) passwd user1  
passwd user2  
2. usermod -a -G wheel user1  
usermod -a -G user1 user2  
3. Права доступа отвечают за то, кто может читать, изменять и выполнять отдельные файлы и папки, на уровне отдельных пользователей или целых групп.  
ls -la
4. Изменить права доступа к файлам можно с помощью команды chmod.  
touch test  
chmod 777 test  
5. root  
6. Необходимо перед нужной командой написать команду sudo (По умолчанию не работает в alt linux)
7. Пользователь root не имеет никаких ограничений
8. sudo userdel -r user2
9. Владельца папки можно изменить с помощью команды chown.  
sudo  chown dlozereg test
