# Postgres

## drop database

May encounter the following error message

```text
ERROR:  database "testdb" is being accessed by other users
DETAIL:  There are 3 other sessions using the database.
```

One method to resolve this is to drop all other active sessions

```sql
SELECT pg_terminate_backend(pg_stat_activity.pid)
FROM pg_stat_activity
WHERE datname='testdb' AND pid<>pg_backend_pid();
```

## docker postgres

### Data I/O

## References

1. [Docker: postgres](https://hub.docker.com/_/postgres)
2. [docker postgres 导出导入数据](https://www.cnblogs.com/zhzhlong/p/11466464.html)

