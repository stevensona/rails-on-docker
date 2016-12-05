# rails5-docker

Content from from https://docs.docker.com/compose/rails/

```bash
docker-compose run web rails new . --force --database=postgresql --skip-bundle
docker-compose build
```

Edit ```config/database.yml```
```yaml
development: &default
  adapter: postgresql
  encoding: unicode
  database: app_development
  pool: 5
  username: postgres
  password:
  host: db

test:
  <<: *default
  database: app_test
  ```
  ```bash
  docker-compose up
  docker-compose run web rake db:create
  ```
  
