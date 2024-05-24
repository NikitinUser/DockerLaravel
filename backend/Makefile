SHELL=/bin/bash

UID := 1000

get-env:
	cp -a ~/env/ws/. .

up:
	env UID=${UID} docker-compose up -d --build --remove-orphans

install:
	docker run --rm -it -v ${PWD}:/app -u ${UID}:${UID} composer install --no-scripts --no-interaction --optimize-autoloader  --ignore-platform-reqs
	env UID=${UID} docker-compose exec -u app service-php php artisan package:discover
	env UID=${UID} docker-compose restart  service-php

require:
	docker run --rm -it -v ${PWD}:/app -u ${UID}:${UID} composer require tymon/jwt-auth  --no-scripts --no-interaction --optimize-autoloader  --ignore-platform-reqs
	env UID=${UID} docker-compose exec -u app service-php php artisan package:discover
	env UID=${UID} docker-compose restart service-php

update:
	docker run --rm -it -v ${PWD}:/app -u ${UID}:${UID} composer update --no-scripts --no-interaction --optimize-autoloader --ignore-platform-reqs
	env UID=${UID} docker-compose exec -u app service-php php artisan package:discover
	env UID=${UID} docker-compose restart service-php

migrate:
	env UID=${UID} docker-compose exec -u app service-php php artisan migrate

migrate-refresh:
	env UID=${UID} docker-compose exec -u app service-php php artisan migrate:refresh

run-seed:
	env UID=${UID} docker-compose exec -u app service-php php artisan db:seed

test:
	env UID=${UID} docker-compose exec -u app service-php php artisan test

