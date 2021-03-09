# Dev note

- generating config.json `make config-reset`
- change docker service: `cp config.mk config.override.mk`

## Start command

```bash
make run-server
```

## Change postgres port

```bash
# change config.override.mk
ENABLED_DOCKER_SERVICES ?= postgres elasticsearch openldap
```

- update postgres port to 5438 in the config.json (`config/config.json`)

```json
{
  "SqlSettings": {
    "DriverName": "postgres",
    "DataSource": "postgres://mmuser:mostest@localhost:5438/mattermost_test?sslmode=disable\u0026connect_timeout=10"
  }
}
```
