## 👋 Welcome to uptime 🚀  

Description  
  
  
## Install my system scripts  

```shell
 sudo bash -c "$(curl -q -LSsf "https://github.com/systemmgr/installer/raw/main/install.sh")"
 sudo systemmgr --config && sudo systemmgr install scripts  
```
  
## Automatic install/update  
  
```shell
dockermgr update uptime
```
  
## Install and run container
  
```shell
mkdir -p "$HOME/.local/share/srv/docker/uptime/rootfs"
git clone "https://github.com/dockermgr/uptime" "$HOME/.local/share/CasjaysDev/dockermgr/uptime"
cp -Rfva "$HOME/.local/share/CasjaysDev/dockermgr/uptime/rootfs/." "$HOME/.local/share/srv/docker/uptime/rootfs/"
docker run -d \
--restart always \
--privileged \
--name casjaysdevdocker-uptime \
--hostname uptime \
-e TZ=${TIMEZONE:-America/New_York} \
-v "$HOME/.local/share/srv/docker/casjaysdevdocker-uptime/rootfs/data:/data:z" \
-v "$HOME/.local/share/srv/docker/casjaysdevdocker-uptime/rootfs/config:/config:z" \
-p 80:80 \
casjaysdevdocker/uptime:latest
```
  
## via docker-compose  
  
```yaml
version: "2"
services:
  ProjectName:
    image: casjaysdevdocker/uptime
    container_name: casjaysdevdocker-uptime
    environment:
      - TZ=America/New_York
      - HOSTNAME=uptime
    volumes:
      - "$HOME/.local/share/srv/docker/casjaysdevdocker-uptime/rootfs/data:/data:z"
      - "$HOME/.local/share/srv/docker/casjaysdevdocker-uptime/rootfs/config:/config:z"
    ports:
      - 80:80
    restart: always
```
  
## Get source files  
  
```shell
dockermgr download src casjaysdevdocker/uptime
```
  
OR
  
```shell
git clone "https://github.com/casjaysdevdocker/uptime" "$HOME/Projects/github/casjaysdevdocker/uptime"
```
  
## Build container  
  
```shell
cd "$HOME/Projects/github/casjaysdevdocker/uptime"
buildx 
```
  
## Authors  
  
🤖 casjay: [Github](https://github.com/casjay) 🤖  
⛵ casjaysdevdocker: [Github](https://github.com/casjaysdevdocker) [Docker](https://hub.docker.com/u/casjaysdevdocker) ⛵  
