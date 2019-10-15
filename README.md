

sudo apt-get update

sudo apt-get install nginx -y
sudo systemctl start nginx

sudo apt-get update

sudo apt install openjdk-8-jdk -y

sudo apt-get install curl -y

curl -sL https://deb.nodesource.com/setup_12.x | sudo -E bash -

sudo apt-get install nodejs -y

sudo sh -c 'echo deb http://pkg.jenkins.io/debian-stable binary/ > /etc/apt/sources.list.d/jenkins.list'

sudo apt-get update

sudo apt install jenkins -y
