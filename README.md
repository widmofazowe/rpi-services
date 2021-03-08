# rpi-services


## Installation

### docker
curl -sSL https://get.docker.com | sh

sudo systemctl enable docker

sudo systemctl start docker

sudo usermod -aG docker pi


### docker-compose
sudo apt-get update

sudo apt-get -yy python python-pip

sudo pip install docker-compose 


