# Nginx and Let's Encrypt with Docker

Support docker-compose (V1) and docker compose (V2)

## Ref

- https://pentacent.medium.com/nginx-and-lets-encrypt-with-docker-in-less-than-5-minutes-b4b8a60d3a71

## Extended Usage

```sh
sudo ./init-letsencrypt.sh \
  -d "[domain_or_subdomain_separated_by_comma]" \
  -e "[your_support_email]"
```

## Prerequisites

- Docker

- docker-compose (V1) or docker compose (V2) as system-wide

- Docker network: `my_net` - driver=bridge ** If use other networks name, replace network section in docker-compose.yml file with it

## Set up steps

1. Start all containers

```sh
docker compose up -d
# replace `docker compose` with `docker-compose` if use docker-compose (V1)
```

2. Get certificate

```sh
sudo ./init-letsencrypt.sh \
  -d "[domain_or_subdomain_separated_by_comma]" \
  -e "[your_support_email]"
```

## FAQ

### How to make docker compose (V2) to be system-wide

```sh
sudo mkdir -p /usr/local/lib/docker/cli-plugins
sudo cp ~/.docker/cli-plugins/docker-compose /usr/local/lib/docker/cli-plugins/docker-compose

# or

sudo mkdir -p /usr/lib/docker/cli-plugins
sudo cp ~/.docker/cli-plugins/docker-compose /usr/lib/docker/cli-plugins/docker-compose
```
