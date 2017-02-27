# rails on docker



```bash
docker-compose run app rails new . --force --database=postgresql --skip-bundle
docker-compose build
```

Edit ```config/database.yml```
```yaml
default: &default
  adapter: postgresql
  encoding: unicode
  pool: <%= ENV.fetch("RAILS_MAX_THREADS") { 5 } %>
  username: postgres
  password:
  host: db
development:
  <<: *default
  database: app_development
test:
  <<: *default
  database: app_test
  ```
  ```bash
  docker-compose up
  docker-compose exec app rails db:create
  ```
  
