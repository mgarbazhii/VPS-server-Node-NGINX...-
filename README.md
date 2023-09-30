# VPS-server-Node-NGINX...-
Config VPS server for Node JS applications

1. Арендуем VPS сервер
2. Подключаемся к серверу с помощью команды
   SSH <name user>@<IP adress>
   2.1. Обновляем пакеты
       sudo apt update
   2.2. Проверяем установленные пакеты в операционной системе
       apt list --installed

        sudo killall <process name>
         killall -s SIGKILL <process name> - если процесс завис
       Удаляем ненужные пакеты
        sudo apt-get remove <package name>
       Чистим пакеты которые не используются
       sudo apt autoremove
   
   2.2. Устанавливаем GIT
       sudo apt install git-all
   2.3. Устанавливаем Node Version Manager
       curl -o- https://raw.githubusercontent.com/nvm-sh/nvm/v0.39.5/install.sh | bash
       Добавляем переменные окружения
       export NVM_DIR="$([ -z "${XDG_CONFIG_HOME-}" ] && printf %s "${HOME}/.nvm" || printf %s "${XDG_CONFIG_HOME}/nvm")"
[ -s "$NVM_DIR/nvm.sh" ] && \. "$NVM_DIR/nvm.sh"
   2.4. Устанавливаем Node JS
       nvm install <node version>
4. Устанавливаем NGINX сервер
   sudo apt install nginx
   Открываем каталог /etc/nginx и правим nginx.conf
   vim nginx.conf
   Запускаем сервер
   sudo systemctl start nginx
   Перезапускаем после любых правок файлов конфигурации
   sudo service nginx restart
    
   Проверяем работоспособность nginx
   systemctl status nginx

   Перезапускаем nginx
   

   Проверяем синтаксис конфигурационных файлов
   
   
