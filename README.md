# Docker

**Firewall (nftables)**

For `nftables` configuration with `DOCKER-USER` chain (which is the default firewall on Debian 11), please refer to `nftables/nftables-docker.conf` in my `config` repository.

**Docker Compose Start**

```
docker compose -p project-name up -d
```


**Update Images and Containers**

The second command will remove all unused containers, networks, images (both dangling and unreferenced).

```
docker compose down
docker system prune -a
docker compose -p project-name up -d
```
