$(shell ! test -e \.env && cat \.\/docker\/docker4drupal\/\.env \.\/docker\/\.env > \.env)
include .env

.PHONY: default pull up stop down clean exec ps

default: up

pull:
	docker-compose pull

up: | pull
	@echo "Starting up containers for for $(PROJECT_NAME)..."
	docker-compose up -d --remove-orphans

stop:
	@echo "Stopping containers for $(PROJECT_NAME)..."
	docker-compose stop

down:
	@echo "Removing containers for $(PROJECT_NAME)..."
	docker-compose down -v --remove-orphans

clean: down

exec:
	docker-compose exec php sh

ps:
	docker-compose ps
