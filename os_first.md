#С авторизацией и загрузкой VAGRANT из России беда. Добавьте пж напоминание об этов в репозиторий задания!!

$ vagrant init bento/ubuntu-20.04
$ vagrant up

HISTFILESIZE на 1133 стоке

ignorespace — не сохранять строки начинающиеся с символа <пробел>
ignoredups — не сохранять строки, совпадающие с последней выполненной командой
ignoreboth — использовать обе опции ‘ignorespace’ и ‘ignoredups’

325 строка {} исполняет команды внутри оболочки. () создает отдельную оболочку внутри которой выполняет команды не влияя на основную (оставляю пояснения себе на будующее).

touch file{1..100000}.txt

Нельзя, максимальное количество аргументов (MAX_ARG_STRLEN) -- 131072
vagrant@vagrant:~$ touch file{1..300000}.txt
bash: /usr/bin/touch: Argument list too long

340 строка [[]] принимает в себя условие и возвращает 0 в данном случает это True и 1 если False (странно, обычно все наоборот)
-d является true если есть файл или директория
Ответом будет 0 если директория есть и 1 если ее нет

vagrant@vagrant:~$ mkdir /tmp/new_path_directory/
vagrant@vagrant:~$ cp /bin/bash /tmp/new_path_directory/
vagrant@vagrant:~$ export PATH="/tmp/new_path_directory/:$PATH"
vagrant@vagrant:~$ type -a bash
bash is /tmp/new_path_directory/bash
bash is /usr/bin/bash
bash is /bin/bash

Изначально прописал патч вначале и он оказался в конце списка. Исправил ошибку и удалил ошибочную строку командой ниже
vagrant@vagrant:~$ export PATH="${PATH%:/tmp/new_path_directory/}"

at запускается один раз в определенное время
batch двыполняет задачи во время периодов низкой загруженности системы; другими словами, когда средний уровень загрузки системы падает ниже значения 1.5 или того значения, которое задано при вызове atd
/usr/sbin/atd -l число 
