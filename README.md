## 👋 Welcome to almalinux 🚀  

almalinux README  
  
  
## Install my system scripts  

```shell
 sudo bash -c "$(curl -q -LSsf "https://github.com/systemmgr/installer/raw/main/install.sh")"
 sudo systemmgr --config && sudo systemmgr install scripts  
```
  
## Automatic install/update  
  
```shell
dockermgr update almalinux
```
  
## Install and run container
  
```shell
mkdir -p "$HOME/.local/share/srv/docker/almalinux/rootfs"
git clone "https://github.com/dockermgr/almalinux" "$HOME/.local/share/CasjaysDev/dockermgr/almalinux"
cp -Rfva "$HOME/.local/share/CasjaysDev/dockermgr/almalinux/rootfs/." "$HOME/.local/share/srv/docker/almalinux/rootfs/"
docker run -d \
--restart always \
--privileged \
--name casjaysdevdocker-almalinux \
--hostname almalinux \
-e TZ=${TIMEZONE:-America/New_York} \
-v "$HOME/.local/share/srv/docker/casjaysdevdocker-almalinux/rootfs/data:/data:z" \
-v "$HOME/.local/share/srv/docker/casjaysdevdocker-almalinux/rootfs/config:/config:z" \
-p 80:80 \
casjaysdevdocker/almalinux:latest
```
  
## via docker-compose  
  
```yaml
version: "2"
services:
  ProjectName:
    image: casjaysdevdocker/almalinux
    container_name: casjaysdevdocker-almalinux
    environment:
      - TZ=America/New_York
      - HOSTNAME=almalinux
    volumes:
      - "$HOME/.local/share/srv/docker/casjaysdevdocker-almalinux/rootfs/data:/data:z"
      - "$HOME/.local/share/srv/docker/casjaysdevdocker-almalinux/rootfs/config:/config:z"
    ports:
      - 80:80
    restart: always
```
  
## Get source files  
  
```shell
dockermgr download src casjaysdevdocker/almalinux
```
  
OR
  
```shell
git clone "https://github.com/casjaysdevdocker/almalinux" "$HOME/Projects/github/casjaysdevdocker/almalinux"
```
  
## Build container  
  
```shell
cd "$HOME/Projects/github/casjaysdevdocker/almalinux"
buildx 
```
  
## Authors  
  
🤖 casjay: [Github](https://github.com/casjay) 🤖  
⛵ casjaysdevdocker: [Github](https://github.com/casjaysdevdocker) [Docker](https://hub.docker.com/u/casjaysdevdocker) ⛵  
