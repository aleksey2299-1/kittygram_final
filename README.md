## Проект Kittygram

Посмотреть на котиков и/или похвастаться своим(своими).

Чтобы похвастаться необходимо зарегистрироваться


### Как запустить проект:

Клонировать репозиторий и перейти в него в командной строке:
````
git clone git@github.com:aleksey2299-1/kittygram_final.git
cd kittygram_final
````
В директории проекта создайте файл .env c данными:
````
POSTGRES_DB=<название db>
POSTGRES_USER=<имя пользователя для db>
POSTGRES_PASSWORD=<пароль пользователя для db>
DB_HOST=db # если поменять, то тогда нужно поменять название сервиса в docker-compose.production.yml
DB_PORT=5432 # это порт по умолчанию для db
SECRET_KEY=<SECRET_KEY в настройках django>
DEBUG=<True или False>
ALLOWED_HOSTS=<ваши адреса через пробел(пример:localhost 127.0.0.1 xxxx.com)>
````


Запустить Docker(чтобы запустить в режиме демона добавьте флаг -d):
````
sudo docker compose -f docker-compose.production.yml up
````


Если Docker не установлен, в терминале linux это можно сделать так:
````
sudo apt update
sudo apt install curl
curl -fSL https://get.docker.com -o get-docker.sh
sudo sh ./get-docker.sh
sudo apt install docker-compose-plugin 
````

### Как начать?

Перейте по адресу localhost:9000/

### Доступ по Api

__Чтобы увидеть информацию нужно зарегистрироваться:__

в теле запроса передать username и password:
````
localhost:8000/api/users/
````
получить token:
````
localhost:8000/api/token/login/
````


Посмотреть всеx котиков:
````
localhost:8000/api/cats/
````

Посмотреть конкретного котика:
````
localhost:8000/api/cats/<номер_котика>/
````

Посмотреть все достижения:
````
localhost:8000/api/achievements/
````

Посмотреть конкретное достижение:
````
localhost:8000/api/achievements/<номер_достижения>/
````
