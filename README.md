# docker-example
Php 7.2 / Apache / Mailhog / MariaDb / Mongo Db / Portainer


docker ps -> Lista container
docker image ls -> Lista immagini

docker-compose up -d -> Up di tutti i container contenuti nel docker-compose file.
docker-compose up -d --build -> Up & build di tutti i container contenuti nel docker-compose file.

docker-compose down

docker restart <nome_container>
docker stop <nome_container>
docker rm <nome_container> (-f -> force)

docker exec -ti <nome_container> bash -> accedere al bash del container
