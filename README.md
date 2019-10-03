# nextcloud

docker-compose nextcloud stack with mariadb and traefik

## Motivation

* host each service as a subdomain of a personal domain over https
* run public maintained images with no modifications
* keep source repo small (2 required files)
* require minimal configuration and setup

## Features

* [Nextcloud](https://hub.docker.com/r/linuxserver/nextcloud/) gives you access to all your files wherever you are.
* [Mariadb](https://hub.docker.com/r/linuxserver/mariadb) is one of the most popular database servers. Made by the original developers of MySQL.
* [Traefik](https://hub.docker.com/_/traefik/) is a modern HTTP reverse proxy and load balancer that makes deploying microservices easy.

## Requirements

* dedicated server or PC with plenty of storage
* windows or linux x86/x64 os (not ARM)
* personal top-level domain with configurable sub-domains (eg. nextcloud.mydomain.com)
* [cloudflare](https://www.cloudflare.com/) or a similar supported [ACME provider](https://docs.traefik.io/configuration/acme/)

## ACME & DNS

Login to your DNS provider ([cloudflare](https://www.cloudflare.com/) in my case), select your domain,
	and add the following DNS Records pointing to your server public IP.

|Type|Name|IPv4 address|TTL|
|---|---|---|---|
|`A`|`nextcloud`|`[server-public-ip]`|`Auto`|
|`A`|`traefik`|`[server-public-ip]`|`Auto`|

## Installation

1. install [docker](https://docs.docker.com/install/linux/docker-ce/debian/)

2. install [docker-compose](https://docs.docker.com/compose/install/#install-compose)

3. clone nextcloud repo
```bash
git clone https://github.com/klutchell/nextcloud.git
```

## Configuration

Copy `env.sample` to `.env` and fill all required fields

```bash
cp env.sample .env && nano .env
```

## Deployment

Pull and deploy containers with docker-compose

```bash
docker-compose pull
docker-compose up -d
```

## Usage

tbd

## Author

Kyle Harding <https://klutchell.dev>

## Acknowledgments

I didn't create any of these docker images myself, so credit goes to the
maintainers, and the original software creators.

* [linuxserver.io](https://linuxserver.io/)
* [traefik.io](https://traefik.io/)

## License

[MIT License](./LICENSE)
