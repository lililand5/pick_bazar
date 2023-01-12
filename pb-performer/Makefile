help:

start:
	@docker compose up -d

logs:
	@docker compose logs -f

stop:
	@docker compose down

bundle:
	@docker exec pb-back bundle

mig: pb-back ## rake db:migrate
	@docker exec pb-back rake db:migrate

c:
	@docker exec -it pb-back rails c

psql:
	@docker exec -it pb-postgres psql -U postgres -d pb_development

rspec:
	@docker exec -e RAILS_ENV=test -e DATABASE_CLEANER_ALLOW_REMOTE_DATABASE_URL=true pb-back rspec

rubocop:
	@docker exec pb-back rubocop

back-sh:
	@docker exec -it pb-back /bin/sh


.PHONY: help

help:
	@grep -E '^[a-zA-Z_-]+:.*?## .*$$' $(MAKEFILE_LIST) | awk 'BEGIN {FS = ":.*?## "}; {printf "\033[36m  %-30s\033[0m %s\n", $$1, $$2}'

pb-back:
	@docker compose up -d pb-back

pb-back-reb:
	@docker compose up -d --build pb-back
