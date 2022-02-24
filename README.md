# Run services using Docker

Run Services using docker on your local machine.

- [Databases](#Databases)
  - [Mongo DB](#1-Mongo-DB)
  - [Postgres](#2-Postgres-DB)
  - [MySQL](#3-MySQL)
  - [Couchbase](#4-Couchbase)

# Run services using docker compose

Run Services using docker compose on your local machine.
- [Bitnami Kafka](docker-compose/docker-compose-bitnami-kafka.yml)


## Databases

### 1. Mongo DB
* Run the MongoDB Container
```
docker run -p 27017:27017 --name mongo -e MONGO_INITDB_ROOT_PASSWORD=root -e MONGO_INITDB_ROOT_USERNAME=root -e MONGO_INITDB_DATABASE=databaseName -d mongo:latest
```
* Open Mongo DB shell in terminal
```
docker exec -it mongo mongo --authenticationDatabase admin -u root -p
```
This command would prompt for a password. So, enter the password you gave before.
### 2. Postgres DB
**Run the below commands to have postgres locally via Docker**
* Run Docker container
```
docker run -d -p 5432:5432 --name postgres -e POSTGRES_PASSWORD='' -e POSTGRES_USER=postgresUserName postgres:latest
```
* Access Postgres container
```
docker exec -it postgres bash
```
* open `psql` as `postgresUserName`
```
psql -U postgresUserName
```
* Create DB
```
create database yourDBName;
```
* Access DB
```
\c yourDBName
```
* Get list of tables
```
\dt
```
### 3. MySQL
* Start MySQL with a root password, the root admin username will be `root`
```
docker run --name mysqlCustomName -e MYSQL_ROOT_PASSWORD=root -d mysql:latest
```
* Start MySQL without a password (But read the logs to see the password)
```
docker run --name mysqlCustomName mysql:latest
```
* To see the logs of MySQL start
```
docker logs mysqlCustomName
```
* Open MySQL console started by Docker
```
docker exec -it mysqlCustomName mysql -u root -p
```
### 4. Couchbase
* Run Couchbase Server docker container
```
docker run -d --name db -p 8091-8094:8091-8094 -p 11210:11210 couchbase
```
* Next, visit http://localhost:8091 on the host machine to see the Web Console to start Couchbase Server setup.
* Official [docker](https://hub.docker.com/_/couchbase) site has further steps in detail 
