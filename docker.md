docker version

Показать все запущенные и остановленные контейнеры
```bash
docker ps -a
```
Показать список образов
```bash
docker images # Простой список
docker images -a # Расширенный список
docker image rm <image ID> # Удалить образ
```
Скачать образ
```bash
docker pull <name_img>
```
Скачать образ, создать контейнер и запустить (производится поиск образа локально, потом на DockerHub)
```bash
docker run --name <custom container name> <image name>
```
Запуск контейнера в режиме Interective Terminal (после запуска SH в контейнере)
```bash
  docker run -i -t <image name>
```
Автоматическое удаление контейнера после остановки
```bash
  docker run --rm <image name>
```
Запуск контейнера в фоновом режиме (Detached - отсоединенный)
```bash
  docker run -d <image name>
```
Запустить команду внутри запущенного контейнера
```bash
  docker exec -it <container ID/name> <команда>
```
  (Пример: Запустить BASH внутри контейнера: docker exec -it 98sf98uv98s bash)
Публикация портов
```bash
  docker run -p <внешний порт>:<контейнер порта> <image name>
```
Подключение томов (папок)
```bash
  docker run -v <локальная папка>:<папка в контейнере> <image name>
```
  (Пример: docker run -v ${PWD}:/usr/share/nginx/html nginx # Вместо папки в контейнере будет текущаю папка)
Информация о запущенном контейнере
```bash
  docker container inspect <container ID/name>
```
Запуск длинной команды
```bash
  docker run \
    -d \
    --name <custom name> \
    -p <внешний порт>:<контейнер порта> \
    -v <локальная папка>:<папка в контейнере> \
    --rm \
    <image name>
```

Внутри контейнера:
```bash
  hostname # Запросить id контейнера
  hostname -i # Запросить IP адрес котейнера
```
Остановить контейнер
```bash
  docker stop <container ID/name>
```
Аварийная остановка
```bash
  docker kill <container ID/name>
```
Посмотреть логи контейнера
```bash
  docker logs <ID контейнера>
```
Удалить контейнер
```bash
  docker rm <CONTAINER ID>
```
Удалить все остановленные контейнеры
```bash
  docker container prune
```
Создание собственного контейнера

Создать файл Dockerfile с содержимым
      FROM <имя базового слоя>:<tag>
      WORKDIR </work directory>
      COPY . . # Копировать файлы из текущей папки в Work Directory
      CMD [ "<имя процесса>", "<параметры>" ] # Запустить процесс в контейнере, например [ "python", "main.py" ]

Сгенерировать Image File
```bash
  docker build \ 
    <директория в которой докер-файлу> # если имя файла стандартное или -f <имя файла>
    -t <image file>:<tag>
```

DOCKER COMPOSE

      version: '3'
      
      services:
        app:
          build: ./app
        mongo:
          image: mongo

```bash
  docker-compose up -d # Запуск в детачт режиме
  docker-compose up -d --build # Запуск с пересборкой образов
  docker-compose down # Остановка и удаление контейнеров
```
  
  
      

