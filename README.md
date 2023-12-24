### Example of consul to Service Discovery

```shell
    docker-compose up -d
```
```shell
    docker exec -it consul01 sh
```
```shell
    consul agent -dev
```
```shell
    consul members
```

#### Install DIG

```shell
    apk -U add bind-tools
```

#### Consult

```shell
    dig @localhost -p 8600 consul01.node.consul
```