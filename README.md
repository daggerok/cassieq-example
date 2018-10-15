# cassieq-example
TODO: CassieQ playground

* _bootstrap CassieQ in docker:_
  ```bash
  docker run -it --rm --name help paradoxical/cassieq help
  docker run -it --rm \
    --name cassieq \
    -p 8080:8080 \
    -p 8081:8081 \
    -p 9042:9042 \
    -e KEYSPACE="demo" \
    -e USERNAME="" \
    -e PASSWORD="" \
    -e CASSANDRA_PORT="9042" \
    paradoxical/cassieq dev
  ```
* create account
  ```bash
  curl -X POST \
    --header 'Content-Type: application/json' \
    --header 'Accept: application/json' \
    -d '"demo"' 'http://localhost:8081/admin/api/v1/accounts'
  ```
* get accounts info
  ```bash
  http :8081/admin/api/v1/accounts
  # or
  curl -X GET \
    --header 'Content-Type: application/json' \
    --header 'Accept: application/json' \
    'http://localhost:8081/admin/api/v1/accounts'
  ```

links:

* [YouTube: CassieQ: The Distributed Message Queue Built on Cassandra (Anton Kropp, Curalate) | C* Summit 2016](https://www.youtube.com/watch?v=LwOq6x-KUAE)
