# Apply a local dump into a PostgreSQL image running on Docker

Assuming that you have a local dump file from PostgreSQL created using pg_dump and want to apply this dump into a docker image running postgresql.

```bash
# I am assuming that your container name is dockerpost and database name is postgres

DOCKER_DB_NAME="$(docker-compose ps -q dockerpost)"
DB_HOSTNAME=postgres
DB_USER=postgres
LOCAL_DUMP_PATH="path/to/local.dump"

docker exec -i "${DOCKER_DB_NAME}" pg_restore -C --clean --no-acl --no-owner -U "${DB_USER}" -d "${DB_HOSTNAME}" < "${LOCAL_DUMP_PATH}"
```
