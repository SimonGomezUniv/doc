 # Play with docker
 
 
 
## using existing image 

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
 7. re-run request on point 3
 8. Are the data lost ?
 9. display information about the first container : where are the data ?
 
 
 TIPS :
 - inside the container, psql is the command to connect
 - docker inspect can provide information

## storing data 

1. Create a volume named postgres_data
2. Launch a first container called postgres_c_1 based on the official postgresql image and attach postgres_data to it.
3. create table users (same as previous)
4. Exit your container and then delete it
5. Run another container called postgres_c_2 and attach postgres_data to it.
6. Log into postgres_c_2 and try to query the table users.
7. Eventhough you destroyed the container that created the initial data, have you lost your db?


TIPS : 
volume should be attached to the following path : /var/lib/postgresql/data

##  image creation

docker is great, how do i package my Motus in docker ?

1. Create a Dockerfile
2. Find a suitable base image
3. Install the right dependencies
4. Run the right command to make it work locally!


## docker Compose
