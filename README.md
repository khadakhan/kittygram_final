[![Main Kittygram workflow](https://github.com/khadakhan/kittygram_final/actions/workflows/main.yml/badge.svg)](https://github.com/khadakhan/kittygram_final/actions/workflows/main.yml)

## О проекте:
Kittygram это сервис разработанный для тех, у кого есть котики. В Kittygram каждый владелец котика может показать остальным зарегистрированным пользователям совего домашнего питомца. Для этого владелец котика должен:
* зарегистрироваться
* аутентифицироваться

* нажать на кнопку "Добавить кота"
* загрузить фотографию своего котика (опционально)
* указать имя котика
* указать год рождения котика
* выбрать наиболее походящий цвет из палитры цветов
* придумать и указать достижение своего котика (опционально)

Каждый владелец котика может указать несколько котиков, если у него дома котоферма. При желании владелец котика может удалять котика из сервиса или редактировать данные о котике.

## Технологии проекта:
* Python
* Django
* DjangoRestFramework
* PostgreSql
* Gunicorn

* Nginx
* Git
* GitHub
* GitHubActions

## Как развернуть проект на сервере: 

Для подключения к Вашему серверу по протоколу SSH Вам понадобятся следующие данные:
* login для подключения к серверу;
* ip - IP-адреc сервера, а также желательно доменное имя;
* passphrase - пароль от закрытого SSH-ключа;
* файл с расширением .pub — открытый SSH-ключ;

* файл без расширения — закрытый SSH-ключ.


Для подключения используйте команду:
```
ssh -i путь_до_файла_с_SSH_ключом/название_файла_закрытого_SSH-ключа login@ip
```

Установите на сервере Docker.

Форкните проект в свой GitHub.

Заполните следующие секреты проекта:
* DOCKER_PASSWORD - пароль для подключения к своему DockerHub;
* DOCKER_USERNAME - username от своего DockerHub;
* HOST - IP-адрес вашего сервера;
* USER - ваш login на сервере;
* SSH_KEY - содержимое текстового файла с закрытым SSH-ключом;
* SSH_PASSPHRASE - passphrase для закрытого ключа;
* TELEGRAM_TO - ID своего телеграм-аккаунта. Узнать свой ID можно у телеграм-бота @userinfobot. Бот станет отправлять уведомления в аккаунт с указанным ID;

* TELEGRAM_TOKEN -  токен вашего бота. Получить этот токен можно у телеграм-бота @BotFather.

### Как заполнить env
На сервере нужно создать два .env файла с данными:

В директории kittygram_backend создать файл .env и указать в нем:
* SECRET_KEY - секретный ключ для шифрования в Django.

* ALLOWED_HOSTS = [IP-адрес сервера, '127.0.0.1', 'localhost', доменное имя сервера] 

В корне проекта создать файл .env и указать в нем:
* POSTGRES_USER - имя пользователя БД (необязательная переменная, значение по умолчанию — postgres);
* POSTGRES_PASSWORD - пароль пользователя БД (обязательная переменная для создания БД в контейнере);
* POSTGRES_DB - название базы данных (необязательная переменная, по умолчанию совпадает с POSTGRES_USER).

* DB_HOST - адрес, по которому Django будет соединяться с базой данных. При работе нескольких контейнеров в сети Docker network вместо адреса указывают имя контейнера, где запущен сервер БД, — в нашем случае это контейнер db;
* DB_PORT - порт, по которому Django будет обращаться к базе данных. 5432 — это порт по умолчанию для PostgreSQL.


### Настроки внешнего шлюза:
Для того чтобы проект заработал на сервере необходимо настроить внешний шлюз для перенаправления запросов в Docker.


Автор проекта: [khadakhan](https://github.com/khadakhan/)