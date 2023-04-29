# Берём за основу образа последнюю версию https://hub.docker.com/_/nginx
FROM nginx

# MAINTAINER устарел: https://docs.docker.com/engine/reference/builder/#maintainer-deprecated
# Указываем человека, ответственного за этот образ
LABEL maintainer="RTKhusaenov@stud.kpfu.ru"

# Копируем конфиг файл в указанную папку
COPY nginx.conf /etc/nginx/

# Запускаем команду для обновления пакетов
# Совмещая команды через &&, экономим место, не создавая излишние слои
RUN apt-get update && apt-get upgrade -y

# Говорим докеру, что контейнер будет слушать этот порт
EXPOSE 80

# Обозначаем volume, который будет использоваться
VOLUME /etc/nginx/nginx.conf

# Говорим докеру, какая команда будет использоваться по умолчанию для запуска контейнера
CMD ["nginx", "-g", "daemon off;"]
