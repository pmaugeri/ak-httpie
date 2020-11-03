# Docker image ak-httpie

This is a lightweight Alpine based Docker package that contains HTTPie and Akamai Edgegrid plugin.

Base Linux distribution: [Alpine 3.9|https://alpinelinux.org/posts/Alpine-3.9.3-released.html]

Main packages included:
* Python v3.6.8
* wget v1.20.3
* [jq](https://stedolan.github.io/jq/)

## Build instructions

```
$ docker build . -t ak-httpie
```

## Usage 

Create a permanent Docker volume to store your credentials:
```
$ docker volume create ak-httpie-volume
```

Run the container:

```
docker run --mount source=ak-httpie-volume,target=/root/data -it ak-httpie
```

NB: the file /root/.edgerc is a symbolic link to /root/data/.edgerc on the persistent volume.