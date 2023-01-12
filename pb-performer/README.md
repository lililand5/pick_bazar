docker exec -it pb-postgres /bin/sh
docker system prune -a
docker exec -it cf43f96f3b4b psql -U postgres default_database