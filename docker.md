docker version

Показать все запущенные и остановленные контейнеры
docker ps -a

Показать список образов 
docker images

Скачать образ 
docker pull <name_img>

Скачать образ, создать контейнер и запустить (производится поиск образа локально, потом на DockerHub)
docker run <name_img>
Запуск контейнера в режиме Interective Terminal (после запуска SH в контейнере)
docker run -i -t <name_img>
Запуск контейнера в фоновом режиме (Detached - отсоединенный)
docker run -d <name_img> 
Остановить контейнер
docker stop <container ID/name>

Удалить контейнер
docker rm <CONTAINER ID>
Удалить все остановленные контейнеры
docker container prune

