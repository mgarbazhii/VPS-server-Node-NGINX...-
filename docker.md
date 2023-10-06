docker version

Показать все запущенные и остановленные контейнеры
docker ps -a

Показать список образов 
docker images

Скачать образ 
docker pull <name_img>

Скачать образ, создать контейнер и запустить (производится поиск образа локально, потом на DockerHub)
docker run --name <custom container name> <name_img> 
Запуск контейнера в режиме Interective Terminal (после запуска SH в контейнере)
docker run -i -t <name_img>
Запуск контейнера в фоновом режиме (Detached - отсоединенный)
docker run -d <name_img> 
Запустить команду внутри запущенного контейнера
docker exec -it <container ID/name> <команда> 
(Пример: Запустить BASH внутри контейнера: docker exec -it 98sf98uv98s bash)
Внутри контейнера:
hostname # Запросить id контейнера
hostname -i # Запросить IP адрес котейнера
Остановить контейнер
docker stop <container ID/name>
Аварийная остановка
docker kill <container ID/name>

Удалить контейнер
docker rm <CONTAINER ID>
Удалить все остановленные контейнеры
docker container prune

