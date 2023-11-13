1. Run DB with Docker using below commands:
```bash
docker pull scylladb/scylla
docker run --name scylla-local -p 9042:9042 -d scylladb/scylla
docker exec -it scylla-local nodetool status
docker exec -it scylla-local cqlsh
CREATE KEYSPACE poc WITH replication = {'class': 'SimpleStrategy', 'replication_factor': 1};
DESC KEYSPACES;
USE poc;
DESC TABLES;
```
2. To run go program:
```go
go mod tidy
go run main.go
```