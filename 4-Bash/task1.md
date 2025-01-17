# Скриптуем по полной

1. Шебанг (shebang) - это особая строка в начале скрипта, которая указывает на необходимый интерпретатор.  
Синтаксис - #!<interpreter> [arguments]
2. Нет, файл может вообще не иметь расширения, но при этом исполняться, но исполняемость влияют права доступа
3. set -euo pipefail  
set -e - останавливает выполнение скрипта, если команда завершилась ошибкой, выводит в stderr строку с ошибкой.  
set -u - останавиливает выполнение скрипта, если встретилась несуществующая переменная  
set -o pipefail - останавливает выполнение скрипта, даже если одна из частей пайпа завершилась ошибкой.  

Создание скрипта:  
touch script  
chmod +x script  
nano script  

Сам скрипт:  
#!/bin/bash  
set -euo pipefail  
cd /home/dlozereg  
ls  
ls -la  
mkdir -p test1/test2  
cd test1/test2  
echo 231 > test  
echo 123 >> test  
echo "Содержимое файла:"  
cat test  
mv test ..  
cd ..  
cp test test2/  
rename test not_a_test test  
echo "Разница:"  
diff -y not_a_test test2/test  
echo "Сортировка:"  
sort test2/test  
echo "Обратная сортировка:"  
sort -r test2/test  
cd ..  
rm -r test1
