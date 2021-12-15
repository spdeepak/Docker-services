# Docker-services

Run Services using docker on your local machine.
- [Databases](#Databases)


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
