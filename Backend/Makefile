install:
	poetry install --no-root

migration:
	poetry run python3 manage.py makemigrations

migrate:
	poetry run python3 manage.py migrate

update: install migration migrate;

super-admin:
	poetry run python3 manage.py createsuperuser

build:
	clear
	docker compose build

start:
	clear
	docker compose up --scale celery_worker=5 --remove-orphans

run: build start;

clear:
	docker compose down --remove-orphans
	clear

server-up:
	docker compose --file docker-compose-production.yml up --scale celery_worker=5 --detach --build

server-down:
	docker compose down --remove-orphans
	clear
