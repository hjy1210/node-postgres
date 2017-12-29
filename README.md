# heroku node and postgres
Following article [Getting Started on Heroku with Node.js](https://devcenter.heroku.com/articles/getting-started-with-nodejs#provision-a-database) and [PostgreSQL and NodeJS](http://mherman.org/blog/2015/02/12/postgresql-and-nodejs/#.WRkPXOWGOK8), create an app, name as hjy-node-postgres, hosted by paas heroku at https://hjy-node-postgres.herokuapp.com.

* create an express based website application
* test application
* create remote website with postgres add-on
* browse remote website

## create an express based website application
#### express node-express
1. use pgAdmin, create a local database node_hero
2. use pgAdmin, create a login role with username hjy and password 1234567890, with previleges login and create database.
3. use SQL shell(psql), database:node_postgres; port:5432; username:hjy; password:1234567890, node_hero=> prompt appeared.
4. node_hero=>CREATE TABLE items(id SERIAL PRIMARY KEY, text VARCHAR(40) not null, complete BOOLEAN);
5. node_hero=>INSERT INTO items(text, complete) values('Yang', false);
6. node_hero=>INSERT INTO items(text, complete) values('Hon', true);
7. Implement a restful website with express-generator.

Note: Default encoding of command prompt is auto, which can not display utf8 characters when using psql. Walk around methods are:
1. chcp 65001
2. set PGCLIENTENCODING=utf8
3. psql *database*

## test application

## create remote website with postgres add-on
#### initial local git repository
`git init`
#### add file .gitignore
#### commit
1. `git add .`
2. `git commit -m "hjy-node-postgres"`
#### create remote "heroku" respository
`heroku create hjy-node-postgress`
#### deploy to heroku
`heroku push heroku master`

#### add-on postgres database 
1. `heroku addons:create heroku-postgresql:hobby-dev`
#### create table items in remote database
1. `heroku pg:psql`
2. `CREATE TABLE items(id SERIAL PRIMARY KEY, text VARCHAR(40) not null, complete BOOLEAN);`
#### insert data in table items
1. `INSERT INTO items(text, complete) values('Yang', false);`
2. `INSERT INTO items(text, complete) values('Hon', true);`

## browse remote website
1. GET　https://hjy-node-postgres.herokuapp.com

2. GET　https://hjy-node-postgres.herokuapp.com/api/v1/todos
3. POST　https://hjy-node-postgres.herokuapp.com/api/v1/todos





