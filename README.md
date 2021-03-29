# rpi-services

## Installation

### docker

curl -sSL https://get.docker.com | sh

sudo systemctl enable docker

sudo systemctl start docker

sudo usermod -aG docker pi

### docker-compose

sudo apt-get install -y libffi-dev libssl-dev

sudo apt-get install -y python3 python3-pip

sudo apt-get remove python-configparser

sudo pip3 -v install docker-compose

### node-red
bash <(curl -sL https://raw.githubusercontent.com/node-red/linux-installers/master/deb/update-nodejs-and-nodered)
sudo systemctl enable nodered.service
npm install -g node-red-contrib-yeelight


### alexa echo node-red routing
npm install -g node-red-contrib-amazon-echo
sudo apt-get install iptables-persistent
sudo iptables -t nat -A PREROUTING -p tcp --dport 80 -j REDIRECT --to-port 8980
sudo iptables -t nat -A PREROUTING -p udp --dport 80 -j REDIRECT --to-port 8980
sudo iptables -t nat -L
sudo sh -c "iptables-save > /etc/iptables.rules"

sudo netfilter-persistent save
sudo netfilter-persistent reload
