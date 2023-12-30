### Example of consul to Service Discovery

```shell
    docker-compose up -d
```

#### Install DIG

```shell
    apk -U add bind-tools
```

#### Consult

```shell
    dig @localhost -p 8600 consul01.node.consul
```


#### Clustering

Server 01:

```shell
    docker exec -it consulserver01 sh
```
```shell
    ifconfig
```
```shell
    consul agent -server -bootstrap-expect=3 -node=consulserver01 -bind=172.26.0.5 -data-dir=/var/lib/consul -config-dir=/etc/consul.d
```

Server 02:

```shell
    docker exec -it consulserver02 sh
```
```shell
    consul agent -server -bootstrap-expect=3 -node=consulserver01 -bind=172.26.0.5 -data-dir=/var/lib/consul -config-dir=/etc/consul.d
```
Join Servers:

```shell
    consul join ip_server_1
```

### Easy Way with JSON:

```shell
    consul agent -config-dir=/etc/consul.d
```
