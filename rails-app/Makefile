################################################################################
# タスク
################################################################################
.PHONY: build
build: ## docker-compose build
	docker-compose build

.PHONY: bash
bash: ## docker-compose run --rm --service-ports app bash
	docker-compose run --rm --service-ports app bash

.PHONY: chown
chown: ## sudo chown -R ${USER}:${USER} ./
	sudo chown -R ${USER}:${USER} ./

.PHONY: down
down: ## docker-compose down
	docker-compose down

.PHONY: s
s: ## bundle exec rails s -b 0.0.0.0
	bundle exec rails s -b 0.0.0.0

################################################################################
# マクロ
################################################################################
# Makefileの中身を抽出してhelpとして1行で出す
# $(1): Makefile名
define help
  grep -E '^[a-zA-Z0-9_-]+:.*?## .*$$' $(1) \
  | grep --invert-match "## non-help" \
  | awk 'BEGIN {FS = ":.*?## "}; {printf "\033[36m%-20s\033[0m %s\n", $$1, $$2}'
endef

################################################################################
# タスク
################################################################################
.PHONY: help
help: ## Make タスク一覧
	@echo '######################################################################'
	@echo '# Makeタスク一覧'
	@echo '# $$ make XXX'
	@echo '# or'
	@echo '# $$ make XXX --dry-run'
	@echo '######################################################################'
	@echo $(MAKEFILE_LIST) \
	| tr ' ' '\n' \
	| xargs -I {included-makefile} $(call help,{included-makefile})
