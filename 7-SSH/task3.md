# Ключики

1. SHH-ключи - наборы символов которые лежат у пользователя и у сервера, сопоставление которых решает, может ли данный пользователь подключиться или нет.  
При использовании ключей можно не вводить каждый раз пароль.  
2. С помощью команды ssh-keygen  
3. ssh-keygen -t ed25519  
Ключи появятся в ~/.ssh  
4. Я использую свой 2 сервер alt linux  
ssh-copy-id -i ~/.shh/id_ed25519.pub student@192.168.1.72 -p 22  
Ключ будет хранится в ~/.ssh/authorized_keys  
5. ssh test (алиас был написан в предыдущем задании)  
Пароль не был запрошен (для ключа я его не создавал)  
6. control sshd-password-auth disabled  
