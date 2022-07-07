# my-docker-set
Create nice Docker Setup on Raspberry Pi 3b


# 1. setup Pi
@dockpi:~ $ sudo apt update && sudo apt upgrade -y

Pc-
#check SSH Keys
ls ~/.ssh
#To generate new SSH keys enter the following command:
ssh-keygen
#The id_rsa file is your private key. Keep this on your computer.
#The id_rsa.pub file is your public key

@dockpi:~ $ sudo rpi-update
@dockpi:~ $ reboot
# 2. install Docker
@dockpi:~ $ curl -fsSL https://get.docker.com -o get-docker.sh| sudo sh get-docker.sh
@dockpi:~ $ sudo groupadd docker | sudo usermod -aG docker $USER

# 3. use Docker Images
  # 3.1 Portainer (Gui for Docker Containers)
  @dockpi:~ $ docker volume create portainer_data
  @dockpi:~ $ docker run -d -p 8000:8000 -p 9000:9000 --name=portainer --restart=always -v /var/run/docker.sock:/var/run/docker.sock -v portainer_data:/data portainer/portainer-ce

  # 3.1 MYST Node
  # 3.1 Homer Dashboard
