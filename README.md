# SurrealDb docker service

This project is a docker image that wraps the surrealDb base image 
into a new one that starts the database automatically with default user 
credentials and in memory mode. It can be used for GitHub actions pipelines to 
setup a testing environment. 

NOTE: This image is only built for the usage with GitHub actions. It is not 
tested for other purposes.

# Usage

You can use the docker container as a service in your action pipeline description.
The default credentials are `root` for both username and password.
```yaml
services:
  surrealdb:
    image: ghcr.io/mathisburger/surrealdb-docker-service:latest
    ports:
      - 127.0.0.1:8000:8000
```

You can also change log-level and database root credentials with environment variables

```yaml
services:
  surrealdb:
    image: ghcr.io/mathisburger/surrealdb-docker-service:latest
    ports:
      - 127.0.0.1:8000:8000
    env:
      LOG_LEVEL: trace
      ROOT_USERNAME: root
      ROOT_PASSWORD: root
```

# License

This project is MIT licensed.
