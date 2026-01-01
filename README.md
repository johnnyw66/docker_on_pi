# docker_on_pi


Commands
=========== 
sudo apt update
sudo apt upgrade -y

Install Docker
===========
curl -sSL https://get.docker.com | sh
sudo usermod -aG docker $USER
docker run hello-world


Install Portainer
===========

docker pull portainer/portainer-ce:latest
docker volume create portainer_data
docker run -d -p 8000:8000 -p 9443:9443 --name=portainer_container --restart=always -v /var/run/docker.sock:/var/run/docker.sock -v portainer_data:/data portainer/portainer-ce:latest


Install NodeRed
===========

docker run -d \
  --name nodered \
  -p 1880:1880 \
  -v nodered_data:/data \
  --restart unless-stopped \
  nodered/node-red:latest

