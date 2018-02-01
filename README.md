Plain Rails on Docker
=====
Template for building plain rails application development environment on Docker.  
In addition, automatic test execution and deployment environment using CricleCI.

## Operation Environment
- Docker version 17.12.0-ce
- docker-compose version 1.18.0
- docker-machine version 0.13.0

## Stack

- Ruby 2.5.0
- Rails 5.1.4

## Readying

```
$ docker pull ruby:2.5.0
```

```
$ git clone https://github.com/shifumin/plain_rails_on_docker
$ cd plain_rails_on_docker
```

## Usage

```
# rails new
$ docker-compose run --rm web rails new . --skip-action-mailer --skip-active-record --skip-test --skip-bundle

# bundle install
$ docker-compose run --rm web bundle install

# rails g
# the following is examples
$ docker-compose run --rm web rails g rspec:install
$ docker-compose run --rm web rails g controller welcome index
$ docker-compose run --rm web rails g model user name:string

# create and start containers
# boot the app (= `rails s`)
$ docker-compose up

# stop and remove containers
$ docker-compose down

# build or rebuild services
# (e.g.: after changing Gemfile or Dockerfile)
$ docker-compose build  # or `docker-compose up --build`
```
