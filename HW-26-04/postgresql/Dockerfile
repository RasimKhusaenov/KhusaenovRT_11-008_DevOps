# Берём за основу образа последнюю версию https://hub.docker.com/_/postgres
FROM postgres

# MAINTAINER устарел: https://docs.docker.com/engine/reference/builder/#maintainer-deprecated
# Указываем человека, ответственного за этот образ
LABEL maintainer="RTKhusaenov@stud.kpfu.ru"

ARG POSTGRES_USER
ARG POSTGRES_PASSWORD
ARG POSTGRES_DB
# Указываем ENV переменные, которые будут использоваться для создания БД
ENV POSTGRES_USER $POSTGRES_USER
ENV POSTGRES_PASSWORD $POSTGRES_PASSWORD
ENV POSTGRES_DB $POSTGRES_DB

# Обозначаем рабочую директорию. Все последующие относительные пути будут начинаться с неё
WORKDIR docker-entrypoint-initdb.d

# Добавляем SQL файл в текущую директорию
ADD world.sql .

# Говорим докеру, что контейнер будет слушать этот порт
EXPOSE 5432
