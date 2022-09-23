# Play with docker
 
 
 
## Using existing image 

1. Launch a postgres database with docker (https://hub.docker.com/_/postgres)
2. log on the database and insert data

```
 CREATE TABLE users (firstname varchar(50) NOT NULL UNIQUE, lastname varchar(50) NOT NULL UNIQUE);
  INSERT INTO
      users(firstname, lastname)
  VALUES
      ('Bob','Kelso'),
      ('Mickey', 'Mouse'),
      ('Lennart', 'Green'),
      ('David', 'Gemmel'),
      ('Randal', 'Munroe');
 ```
 
 3. query the data you ve just inserted
 4. exit te container
 5. stop the container
 6. create and run another postgres container
 7. run the same request as point 3 in the new container
 8. Are the data lost ?
 9. display information about the first container : where are the data ?
 
 
 TIPS :
 - inside the container, psql is the command to connect
 - docker exec can help
 - docker inspect can provide information

## Storing data 

1. Create a volume named postgres_data
2. Launch a first container called postgres_c_1 based on the official postgresql image and attach postgres_data to it.
3. create table users (same as previous)
4. Exit your container and then delete it
5. Run another container called postgres_c_2 and attach postgres_data to it.
6. Log into postgres_c_2 and try to query the table users.
7. Eventhough you destroyed the container that created the initial data, have you lost your db?


TIPS : 
volume should be attached to the following path : /var/lib/postgresql/data

## Image creation

docker is great, how do i package my Motus in docker ?

1. Create a Dockerfile
2. Find a suitable base image
3. Install the right dependencies
4. Run the right command to make it work locally!


## Docker Compose - step 1

the great recipe
goal is to have a PostgreSQL database and NocoDB interface running at once.
NocoDB is an open source interface to connect to any sql DB, allowing to store and manage data. 

Write a Docker-Compose with two services
- postgres for the db
- no_codb for the interface

### NocoDB

1. Pull up the nocodb images
2. Open a port mapping: 8080:8080
3. Make it dependant on: postgres service
4. Always restart service if anything happens
5. Create a volume called nc_data and attach it at this location: /usr/app/data
6. Define an environment variable called NC_DB with the path corresponding to your db.
 - pg://host.docker.internal:5432?u=postgres&p=postgres&d=root_db

Note :
- 5432 corresponds to the port of your db
- u means username
- p means password
- d means db

### Postgres

1. Pull up the postgres images
2. Open port mapping 5432:5432
3. Define the env variables
- POSTGRES_DB
- POSTGRES_PASSWORD
- POSTGRES_USER
4. Create a volume called postgres_data and attach it at this location: /var/lib/postgresql/data:rw

Test your interface on [http://localhost:8080](http://localhost:8080)


## Docker Compose - step 2

Let's apply this to the motus project 

1. Create a Docker-compose file in your motus App folder
2. import your docker image
3. Run your docker-compose file

You will improve this Docker-compose later on 






