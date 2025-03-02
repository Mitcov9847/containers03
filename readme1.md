# Отчет по работе с Docker

### 1.1 Установка Docker Desktop

Перед началом работы я установил **Docker Desktop**. Для этого загрузил установщик с официального сайта:  
            🔗[https://www.docker.com/products/docker-desktop/](https://www.docker.com/products/docker-desktop/)🔗

После установки я проверил корректность работы Docker, выполнив в терминале команду:  docker --version

![alt text](/image/image.png)
Результат, который я получил:

## 2. Клонирование репозитория
2.1 Клонирование через git clone
Затем я открыл терминал (cmd) и выполнил команду:
git clone https://github.com/Mitcov9847/containers03.git

Результат, который я получил:
![alt text](/image/image-1.png)

## 3. Создание Dockerfile и структуры проекта

#### 3.1 Создание Dockerfile
Я создал файл Dockerfile в корневой папке containers03 и добавил в него следующий код:
FROM debian:latest
COPY ./site/ /var/www/html/
CMD ["sh", "-c", "echo hello from $HOSTNAME"]
![alt text](/image/image-2.png)

### 3.2 Создание папки site и index.html

Я создал папку site и файл index.html с помощью следующих команд:

mkdir site echo "<h6>Привет, Docker!</h6>" > site/index.html

После этого я проверил содержимое папки:
![alt text](/image/image-3.png)

## 4. Сборка Docker-образа

Для сборки Docker-образа я выполнил команду:
docker build -t containers03 .
![alt text](/image/image-4.png)
Успешная сборка Docker-образа

## 5. Запуск контейнера и тестирование

### 5.1 Запуск контейнера

Я запустил контейнер и проверил его работу, выполнив команду:

docker run --name containers03 containers03
![alt text](/image/image-5.png)
Запуск контейнера и вывод сообщения

1️⃣ Я удалил контейнер перед повторным запуском:
![alt text](/image/image-6.png)

2️⃣ Затем я запустил контейнер в интерактивном режиме (bash):
![alt text](/image/image-8.png)

3️⃣ Внутри контейнера я выполнил следующие команды:
![alt text](/image/image-9.png)
Проверка файлов внутри контейнера

4️⃣ После этого я вышел из контейнера:

exit

## 6. Итоги работы

### В результате выполнения лабораторной работы я научился:
1. Устанавливать и настраивать Docker.
2. Создавать Dockerfile и собирать Docker-образы.
3. Работать с контейнерами и проверять их содержимое.

Контейнер работает корректно, файл index.html успешно передан внутрь контейнера и отображается в его файловой системе.

## 7. Используемые источники
1. Официальная документация Docker: https://docs.docker.com/
2. Репозиторий проекта на GitHub: https://github.com/Mitcov9847/containers03
