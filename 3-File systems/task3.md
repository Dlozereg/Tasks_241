# Продолжаем

1. cat /etc/fstab  
fstab содержит информацию о различных файловых системах и устройствах хранения информации на компьютере.
2. В систему был добавлен диск
3. fdisk -l  
Disk /dev/sdb: 7.22 GiB, 7747928064 bytes, 15132672 sectors  
4. fdisk /dev/sdb  
n  
1  
w  
mkfs.ext4 /dev/sdb1  
5. mkdir /mnt/flash  
mount /dev/sdb1 /mnt/flash  
6. cd /mnt/flash  
touch test.txt  
7. umount /mnt/flash  
файл сохранился
8. nano /etc/fstab  
В конец файла - /dev/sdb1 /mnt/flash ext4 defaults 0 0
9. All is correct  
10. После перезагрузки диск остался примонтирован
