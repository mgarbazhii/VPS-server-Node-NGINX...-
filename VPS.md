##### Config VPS server for Node JS applications

### 1. Арендуем VPS сервер

### 2. Подключаемся к серверу с помощью команды  
```bash
      ssh <name user>@<IP adress or domain name>
```
   
### 3. Подготовка операционной системы 
```bash   
apt list --installed  #Проверяем установленные пакеты 
```
   Убиваем процессы не нужные на сервере (например, часто устанавливают по умолчанию apache2)
      `sudo killall <process name>`
   - если процесс завис
      `sudo killall -s SIGKILL <process name>` 
       
   Удаляем ненужные пакеты
      `sudo apt-get purge apache2*`
      или
      `sudo apt-get remove <package name>`

   Чистим пакеты которые не используются
      `sudo apt autoremove`

   Обновляем пакеты
      `sudo apt update`

   Устанавливаем GIT
      `sudo apt install git-all`

   Устанавливаем Node Version Manager
      `curl -o- https://raw.githubusercontent.com/nvm-sh/nvm/v0.39.5/install.sh | bash`
   - добавляем переменные окружения
      `export NVM_DIR="$([ -z "${XDG_CONFIG_HOME-}" ] && printf %s "${HOME}/.nvm" || printf %s "${XDG_CONFIG_HOME}/nvm")"
[ -s "$NVM_DIR/nvm.sh" ] && \. "$NVM_DIR/nvm.sh"`
   
   Устанавливаем Node JS
      `nvm install <node version>`

   Устанавливаем NGINX сервер
      `sudo apt install nginx`
   - открываем каталог /etc/nginx и правим nginx.conf
      `nano nginx.conf`
   - проверяем синтаксис конфигурационных файлов
      `sudo nginx -t`
   - запускаем сервер
      `sudo systemctl start nginx`
   - перезапускаем после любых правок файлов конфигурации
      `sudo service nginx restart`
   - проверяем работоспособность nginx
      `systemctl status nginx`

### 4. 
   
`ssh -T git@github.com`  --- проверить, что пересылка работает с сервером 
`cat id_rsa.pub|pbcopy` ---- копируем ключ из файла в буфер обмена

[MyLink]: <http://expressjs.com>
[git-repo-url]: <https://github.com/joemccann/dillinger.git>  
   
