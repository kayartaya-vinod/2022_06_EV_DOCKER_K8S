docker inspect mysql8server | grep IPAddress

docker network ls

docker network create vinod_network_1

docker network inspect vinod_network_1

docker inspect mysql8server

docker network connect vinod_network_1 mysql8server

docker network inspect vinod_network_1

docker network rm vinod_network_1

docker network disconnect vinod_network_1 mysql8server

docker network rm vinod_network_1
