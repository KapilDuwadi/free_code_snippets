
### Running postgres docker container and connecting from PgAdmin

```
docker run --name some-postgres -e POSTGRES_PASSWORD=mysecretpassword -d -p 5432:5432 postgres
```
Default postgres user: postgres
Default database: postgres

Login to PgAdmin UI with following information

- Host: localhost
- Port: 5432 (specify different port if other ports are used)
- Maintenance database: postgres
- Username: postgres (specify different username if necessary)
- Password: mysecretpassword (specify different password if necessary)


### Running MySQL docker container and connecting from MySQL Workbench
```
docker run --name some-mysql -e MYSQL_ROOT_PASSWORD=mysecretpassword -d -p 3306:3306 mysql:latest
```

Login to MySQL workbench with following information
- Host name: 127.0.0.1 (Chage if necessary)
- Port: 3306 (Change if necessary)
- Username: root (Change if necessary)
- Password: mysecretpassword (Change if necessary)


### Running REDIS docker container
```
docker run --name some-redis -d -p 6379:6379 redis
```