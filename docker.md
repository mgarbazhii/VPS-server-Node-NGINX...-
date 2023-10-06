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
Запуск контейнера в фоновом режиме (Detached - отсоединенный)
docker run -d <image name> 
Запустить команду внутри запущенного контейнера
docker exec -it <container ID/name> <команда> 
(Пример: Запустить BASH внутри контейнера: docker exec -it 98sf98uv98s bash)
Публикация портов
docker run -p <внешний порт>:<контейнер порта> <image name>
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

