Урок 4. Dockerfile и слои
Задание: необходимо создать Dockerfile, основанный на любом образе (вы в праве выбрать самостоятельно).
В него необходимо поместить приложение, написанное на любом известном вам языке программирования (Python, Java, C, С#, C++).
При запуске контейнера должно запускаться самостоятельно написанное приложение.

Параметры загрузки Dockerfile на примере alpine:
FROM alpine:latest
FROM python:3
ADD homework4.py /
CMD [ "python", "homework4.py" ] root@gb-linux:~home/andrey/dockerfiles$







//////////////////////////////////////////////////////////////////

Пример
FROM ubuntu:22.10
RUN apt-get update && \
apt-get install -y cowsay && \
ln -s /usr/games/cowsay /usr/bin/cowsay && \
rm -rf /var/lib/apt/lists/*
CMD [“cowsay”]
FROM ubuntu:22.10
: Указывает базовый образ, на основе которого будет создан новый образ. В данном случае используется образ Ubuntu версии 22.10.
RUN apt-get update &&
: Обновляет список пакетов в системе.
apt-get install -y cowsay &&
: Устанавливает пакет "cowsay" в систему. Опция -y указывает на автоматическое подтверждение при установке.
ln -s /usr/games/cowsay /usr/bin/cowsay &&
: Создает символическую ссылку /usr/bin/cowsay, чтобы можно было запускать команду cowsay из любого места в системе.
rm -rf /var/lib/apt/lists/*
: Удаляет временные файлы, скачанные во время установки пакетов, чтобы сэкономить место в образе.
CMD "cowsay"
: Задает команду по умолчанию для запуска при запуске контейнера. В данном случае, при запуске контейнера будет выполнена команда cowsay.



docker run: Запускает контейнер из образа.
Пример: docker run my-image

docker start: Запускает остановленный контейнер.
Пример: docker start my-container

docker stop: Останавливает запущенный контейнер.
Пример: docker stop my-container

docker restart: Перезапускает контейнер.
Пример: docker restart my-container

docker pause: Приостанавливает выполнение контейнера.
Пример: docker pause my-container

docker unpause: Возобновляет выполнение приостановленного контейнера.
Пример: docker unpause my-container

docker exec: Запускает команду внутри работающего контейнера.
Пример: docker exec -it my-container bash

docker attach: Присоединяется к работающему контейнеру и подключается к его выводу.
Пример: docker attach my-container

docker logs: Выводит логи контейнера.
Пример: docker logs my-container
