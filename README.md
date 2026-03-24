1. Сигналы и процесс `top` (`SIGSTOP``SIGCONT``SIGTERM/SIGKILL`)
 - kill -STOP 3201
 - kill -CONT 3201
 - kill -15 3201
 - kill -9 3201

2. Установка nginx и вывод процессов
 - sudo apt update && sudo apt install nginx -y
 - ps -eo ppid,pid,args | grep nginx
3. Дерево процессов
 - pstree -pa | grep nginx
4. Убийство master-процесса
 - ps -ef | grep "nginx: master process"
 - sudo kill 27492
 - systemctl status nginx
5. Запуск процесса
 - sudo systemctl start nginx
6. Убийство воркера
 - nginx: worker process
 - sudo kill 28540
 - ps -ef | grep nginx
7. Управление заданиями `(Job Control)`
 - Запустить процесс `sleep 3000`
 - Остановить процесс `Ctrl + Z`
 - Вывести список jobs `jobs`
 - Перевести в background `bg %1`
 - Вытащить в foreground: `fg %1`
    Задача со звездочкой
8. Установка, создание `unit-файла`, запуск
 - sudo cp /etc/redis/redis.conf /etc/redis/redis-second.conf
 - sudo apt install redis-server -y
 - sudo nano /etc/systemd/system/redis-second.service
 - sudo systemctl daemon-reload
 - sudo systemctl start redis-second
 - sudo systemctl enable redis-second
