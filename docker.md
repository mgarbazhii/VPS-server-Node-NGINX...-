docker version

Показать все запущенные и остановленные контейнеры
docker ps -a

Показать список образов 
docker images # Простой список
docker images -a # Расширенный список
docker image rm <image ID> # Удалить образ



Скачать образ 
docker pull <name_img>

Скачать образ, создать контейнер и запустить (производится поиск образа локально, потом на DockerHub)
docker run --name <custom container name> <image name> 
Запуск контейнера в режиме Interective Terminal (после запуска SH в контейнере)
  docker run -i -t <image name>
Автоматическое удаление контейнера после остановки
  docker run --rm <image name>
Запуск контейнера в фоновом режиме (Detached - отсоединенный)
  docker run -d <image name> 
Запустить команду внутри запущенного контейнера
  docker exec -it <container ID/name> <команда> 
  (Пример: Запустить BASH внутри контейнера: docker exec -it 98sf98uv98s bash)
Публикация портов
  docker run -p <внешний порт>:<контейнер порта> <image name>
Подключение томов (папок)
  docker run -v <локальная папка>:<папка в контейнере> <image name>
  (Пример: docker run -v ${PWD}:/usr/share/nginx/html nginx # Вместо папки в контейнере будет текущаю папка)
Информация о запущенном контейнере
  docker container inspect <container ID/name>
Запуск длинной команды
  docker run \
    -d \
    --name <custom name> \
    -p <внешний порт>:<контейнер порта> \
    -v <локальная папка>:<папка в контейнере> \
    --rm \
    <image name>

Внутри контейнера:
  hostname # Запросить id контейнера
  hostname -i # Запросить IP адрес котейнера
Остановить контейнер
  docker stop <container ID/name>
Аварийная остановка
  docker kill <container ID/name>

Посмотреть логи контейнера
  docker logs <ID контейнера>

Удалить контейнер
  docker rm <CONTAINER ID>
Удалить все остановленные контейнеры
  docker container prune

Создание собственного контейнера

Создать файл Dockerfile с содержимым
      FROM <имя базового слоя>:<tag>
      WORKDIR </work directory>
      COPY . . # Копировать файлы из текущей папки в Work Directory
      CMD [ "<имя процесса>", "<параметры>" ] # Запустить процесс в контейнере, например [ "python", "main.py" ]

Сгенерировать Image File
  docker build \ 
    <директория в которой докер-файлу> # если имя файла стандартное или -f <имя файла>
    -t <image file>:<tag>

DOCKER COMPOSE

      version: '3'
      
      services:
        app:
          build: ./app
        mongo:
          image: mongo

  docker-compose up -d # Запуск в детачт режиме
  docker-compose up -d --build # Запуск с пересборкой образов
  docker-compose down # Остановка и удаление контейнеров

  
  
      

