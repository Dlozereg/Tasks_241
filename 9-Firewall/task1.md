
# Открываем iptables

1. iptables уже было установлено и на клиенте, и на сервере (я подключался к своему 2 серверу alt linux).  
2. ssh test (алиас был создан ранее)  
Подключение работает.  
3. Возможно, все внешние подключения станут запрещены, пока iptables не будет настроен.  
4. iptables -A INPUT -p tcp --dport 22 -j ACCEPT  
5. Я указал TCP порт. 

# Сохраняем

6. reboot  
Не сохранилось.  
7. iptables-save >> /etc/sysconfig/iptables  
