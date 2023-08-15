<div id="header" align="center">
  <img src="https://media.giphy.com/media/M9gbBd9nbDrOTu1Mqx/giphy.gif" width="100"/>
</div>
<div id="badges" align="center">
  <img src="https://img.shields.io/badge/Python-blue?style=for-the-badge&logo=python&logoColor=yellow" alt="Python"/>
  <img src="https://img.shields.io/badge/React-white?style=for-the-badge&logo=react&logoColor=blue" alt="React"/>
  <img src="https://img.shields.io/badge/Django-dark_green?style=for-the-badge&logo=django&logoColor=white" alt="Django"/>
  <img src="https://img.shields.io/badge/Docker-blue?style=for-the-badge&logo=docker&logoColor=white" alt="Docker"/>
  <img src="https://img.shields.io/badge/PostgreSQL-white?style=for-the-badge&logo=postgresql&logoColor=blue" alt="PostgreSQL"/>

<a href="https://git.io/typing-svg"><img src="https://readme-typing-svg.herokuapp.com?font=Fira+Code&size=25&pause=500&color=F70000&center=true&vCenter=true&width=435&lines=Kittygram" alt="Kittygram" /></a>
</div>


### Описание:
Социальный сайт для публикации фотограций котиков с их достижениями.

### Технологии используемые в проекте:
- Django==3.2.3
- djangorestframework==3.12.4
- djoser==2.1.0
- webcolors==1.11.1
- Pillow==9.0.0
- pytest==6.2.4
- pytest-django==4.4.0
- pytest-pythonpath==0.7.3
- gunicorn==20.1.0
- python-dotenv==1.0.0
- nodejs==v18.17.0
- npm==9.6.7
- PostgreSQL==13
- Docker

### Инструкция по деплою
1) Установите curl, docker и docker-compose-plugin
```
sudo apt update && sudo apt install curl
```
```
curl -fSL https://get.docker.com -o get-docker.sh && sudo sh ./get-docker.sh
```
```
sudo apt-get install docker-compose-plugin
```
2) Перейдите в папку `kittygram` и скопируйте `.env.example` в `.env`. Заполните его своими данными

3) Создайте и скопируйте содержимое `docker-compose.production.yml` удобым вам способом в корневую папку `kittygram` и запустите установку контейнеров продакшн версии
```
sudo docker compose -f docker-compose.production.yml up -d
```
4) Примените миграции, создайте статические файлы для админки и скопируйте статику в директорию веб-сервера
```
sudo docker compose -f docker-compose.production.yml exec backend python manage.py migrate
```
```
sudo docker compose -f docker-compose.production.yml exec backend python manage.py collectstatic
```
```
sudo docker compose -f docker-compose.production.yml exec backend cp -r /app/collect_static/ /static_backend/static/
```
5) Создайте суперпользователя
```
sudo docker compose -f docker-compose.production.yml exec backend python manage.py createsuperuser
```

### Автор:
#### Первоначальное авторское право © 2020 Яндекс.Практикум <https://github.com/yandex-praktikum>
#### Раздвоенное авторское право © 2023 Quality <mr.quality@ya.ru>