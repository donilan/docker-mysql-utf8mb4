# docker-mysql-utf8mb4

the latest build of this image is mysql 5.7. this for gitlab-ci only,
gitlab-ci config as below.

``` yaml
rspec:
  stage: test
  image: ruby:2.3
  services:
    - donilan/mysql-utf8mb4
  variables:
    MYSQL_ALLOW_EMPTY_PASSWORD: "true"
    MYSQL_DATABASE: "db_name"
    DB_HOST: donilan-mysql-utf8mb4
  before_script:
    - ruby -v
    - bundle exec rake db:create db:migrate

  script:
    - bundle exec rspec spec --profile
```
