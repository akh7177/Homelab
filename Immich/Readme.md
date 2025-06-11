# Immich installation and setup

*(If you haven't looked upon setting up Ubuntu Server VM and doing a GPU passtrhough to it have a look over [here](../Jellyfin/Readme.md) and then return as we'll be using the same VM as well as the GPU)*

**Step 1** : Install docker on to the Ubuntu Server VM by following *[this]*(https://docs.docker.com/engine/install/ubuntu/#install-using-the-convenience-script) official installation guide

**Step 2** : Make a directory for immich and navigate to it

**Step 3** : Get the docker compose, .env, harware encdoding and hardware accelerated ML yaml files with these commands

```bash

wget -O docker-compose.yml https://github.com/immich-app/immich/releases/latest/download/docker-compose.yml 
wget -O .env https://github.com/immich-app/immich/releases/latest/download/example.env

wget -O hwaccel.transcoding.yml https://github.com/immich-app/immich/releases/latest/download/hwaccel.transcoding.yml

wget -O hwaccel.ml.yml https://github.com/immich-app/immich/releases/latest/download/hwaccel.ml.yml

```
**Step 4**: Checkout the compose file that I've uploaded above to make changes in ur respecitive system to match ur requirements and once u've configured the compose and .env files, deploy the containers with *docker compose up -d*

That's it! The Immich Server will be running and accessible at http://<Ubuntu_Server_VM_IP>:2283!

*(Setup [tailscale](../Tailscale/Readme.md) and map the service to a custom domain using [NPM](../Nginx_Proxy_Manager/Readme.md) for improving QoL)*