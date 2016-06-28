# pgVersions

Try out any of PostgreSQL 9.x version in a snap.

## Dependencies

This script assumes you have docker installed on your machine.

## Usage

### Initiate a new database

```bash
> multi_pg_ctl initdb -v 9.4 -d a_database -u user -p password
Docker volume pg-9.4-data created.
Docker container pg-9.4 running.
```

### List running postgres server

```bash
> multi_pg_ctl status
RUNNING DATABASES
172.17.0.4      pg-9.4              3eabba686bc2

EXISTING VOLUMES
pg-9.4-data
```

### CLI

_TODO_ This is a work in progress and is not implemented yet

```bash
> multi_pg_ctl psql -v 9.4
psql (9.4.8)
Type "help" for help.

postgres=#
```

### Stop a running postgres

```bash
> multi_pg_ctl stop -v 9.4
Docker container pg-9.1 stopped.
```

### Destroy a postgres server

WARNING: This will destroy the volume data attached.

```bash
> multi_pg_ctl destroy -v 9.4
```

## Rational

Here are the needs that led me to write this script:

* Easily simulate a multiple version postgresql cluster
* Wanting to do some testing with any postgresql version on my machine
* No system installation

## License

[MIT License](https://github.com/paulRbr/pgversions/blob/master/LICENSE)
