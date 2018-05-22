# Steps

## Building Image

Build image `ubuntu-ping`

```
docker image build -t ubuntu-ping . 
```

## Creating Network

Create docker network called `mynet123` with a sub-net `172.18.0.0/16`

```
docker network create --subnet=172.18.0.0/16 mynet123
```

## Running Container

Run one container called `node1` with IP `172.18.0.2` and linked to `mynet123`

```
docker container run -d -it --net mynet123 --ip 172.18.0.2 --name node1 ubuntu-ping
```

## Running Another Container

Run another container called `node2` with IP `172.18.0.3` and linked to `mynet123`

```
docker container run -d -it --net mynet123 --ip 172.18.0.3 --name node2 ubuntu-ping
```

## Verifying Ping Connection

Access to container `node1`

```
docker container attach node1
```

Ping from `node1` to `node2` using IP address

```
ping 172.18.0.3
```

Ping from `node1` to `node2` using container's name

```
ping node2
```
