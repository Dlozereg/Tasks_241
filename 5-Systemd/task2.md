# Пишем юниты

1. touch new_script  
chmod +x new_script  
nano new_script  

Содержимое скрипта:  
#!/bin/bash  
set -euo pipefail  
cd "$(dirname "$0")"  
if ! [ -d info/ ]; then  
mkdir info  
fi  
cd info  
if ! [ -f 1 ]; then  
date > 1  
fi  
if ! [ -f 2 ]; then  
uname -r > 2  
fi  
if ! [ -f 3 ]; then  
uname -n > 3  
fi  
if ! [ -f 4 ]; then  
ls -la ~ > 4  
fi  
2. nano /etc/systemd/system/my.service  

Содержимое юнита:  
[Unit]  
Description=my own cool unit  

[Service]  
Type=oneshot  
ExecStart=/home/dlozereg/new_script  

[Install]  
WantedBy=multi-user.target


systemctl start my    
3. nano /etc/systemd/system/my.timer  

Содержимое таймера:  
[Unit]  
Description=my own nice timer  
Requires=my.service  

[Timer]  
Unit=my.service  
OnCalendar=*:0/5  

[Install]  
Wantedby=timers.target  
4. По умолчанию юниты вызываются от рута.  
5. useradd -m myuser  
passwd myuser  
6. Скрипт пришлось переносить в домашнюю директорию нового юзера, иначе бы нужен был sudo.  
В сервисе было дописано:  
[Unit]  
User=myuser  
Group=myuser  
...  
ExecStart=/home/myuser/new_script  

systemctl daemon-reload  
systemctl start my.service  
7. В начале скрипта:  
cd ~  
