# Docker Official example

Work directory: official-example/traefik.yml

## How to

### Start Traefik

```sh
docker run -d -p 8080:8080 -p 80:80 \
-v $PWD/traefik.yml:/etc/traefik/traefik.yml \
-v /var/run/docker.sock:/var/run/docker.sock \
traefik:v2.5
```

### Start Backend service without any expose port

```sh
docker run -d --name test traefik/whoami
```

### Try to curl and done~

curl to Traefik instance at host `test.docker.localhost`

```sh
curl --header 'Host:test.docker.localhost' 'http://localhost:80/'
```

## Ref

https://hub.docker.com/_/traefik
