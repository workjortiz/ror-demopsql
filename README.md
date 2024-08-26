# README

Default Project With PostgreSQL connector

Require Installation 
* Ruby 3.1.4
* Rails 7.0.8.4
* Recommend use RVM

Execute [bundle install] to install dependecies
Run using [rails s]

The project contain a default model [Post.rb] for test DB connection using the command [rake db:migrate]

You can rollback the migration using [rake db:rollback]

Modified Database.yml as require on "development" section

development:
  <<: *default
  host: 0.0.0.0
  port: 4040
  database: dbdock
  username: tester
  password: 123


----------------[RUN WITH DOCKER COMPOSE]-------------------
[docker-compose.yml]
[Command >>> docker compose up]

services:
  db-postgres:
    image: postgres:latest
    container_name: dock-port-4040
    volumes:
    - pgdata:/var/lib/postgresql/data
    restart: always
    ports:
    - '4040:5432'
    environment:
    - POSTGRES_DB=dbdock
    - POSTGRES_USER=tester
    - POSTGRES_PASSWORD=123

volumes:
  pgdata:
  
