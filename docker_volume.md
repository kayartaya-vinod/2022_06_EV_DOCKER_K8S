ls mysql_datafiles

-- doesnt show any files

docker run -d --name mysql8server -v /root/mysql_datafiles:/var/lib/mysql -e MYSQL_ROOT_PASSWORD=Welcome#123 mysql:latest

-- now on your /root/ folder you should see /mysql_datafiles folder consisting of lots of mysql files (created by mysql server)

docker exec -it mysql8server mysql -uroot -pWelcome#123

-- create database trainingdb;
-- use trainingdb;
-- create table persons(id int, name varchar(50));
-- insert into persons values (1, 'Vinod'), (2, 'Shyam');
-- exit -- to come back from mysql cli to host os (ubuntu)

ls mysql_datafiles

-- check the content for trainingdb folder and related db files

docker rm -f mysql8server

-- stop and remove the container (no snapshot saved)

docker run -d --name mysql8server -v /root/mysql_datafiles:/var/lib/mysql -e MYSQL_ROOT_PASSWORD=Welcome#123 mysql:latest

-- create a new container, but link the same to the volume on your host os

docker exec -it mysql8server mysql -uroot -pWelcome#123 trainingdb

-- you should be in trainingdb database, and should see tables (show tables) and records (select \* from persons)
