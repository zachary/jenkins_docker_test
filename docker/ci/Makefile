CONTAINER := game_php
 
build:
	@docker-compose up -d
 
composer:
	@docker exec -i $(CONTAINER) composer install
 
test:
	@docker exec -i $(CONTAINER) vendor/bin/php-cs-fixer fix src --rules=@PSR2 --using-cache=no --dry-run --verbose --diff
	@docker exec -i $(CONTAINER) vendor/bin/phpunit tests
	@docker exec -i $(CONTAINER) vendor/bin/phpstan analyse src tests --no-progress --level=max
	@make -s down
 
down:
	@docker-compose down --volumes
	@make -s clean
 
clean:
	@docker system prune --volumes --force
