# fabric8io_docker-maven-plugin_1517
Small reproducer for https://github.com/fabric8io/docker-maven-plugin/issues/1517

## Steps

1. `cd one`
2. `mvn docker:build docker start`
3. `cd ../other`
4. `mvn docker:stop`

## Expected

`docker ps` output does not show instances of test-redis running.

## Actual

```shell
$ docker ps
CONTAINER ID   IMAGE                    COMMAND                  CREATED         STATUS         PORTS                                                                                            NAMES
55ef28d6452a   test-redis               "docker-entrypoint.s?"   7 minutes ago   Up 7 minutes   0.0.0.0:6379->6379/tcp, :::6379->6379/tcp                                                        test-redis-1
```
