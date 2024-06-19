# 1. How To Install Nginx on Ubuntu 22.04

## Step 1 – Installing Nginx
```sh
sudo apt update

sudo apt install nginx
```

## Step 2 – Managing the Nginx Process
```sh
sudo systemctl stop nginx

sudo systemctl start nginx

sudo systemctl restart nginx

sudo systemctl reload nginx

sudo systemctl disable nginx

sudo systemctl enable nginx
```

## Step 3 - Config Nginx
```sh
sudo ln -s /etc/nginx/sites-available/your_domain /etc/nginx/sites-enabled/
```

# 2. How To Install and Use Docker on Ubuntu 22.04

## Step 1 — Installing Docker
```sh
sudo apt update

sudo apt install apt-transport-https ca-certificates curl software-properties-common

curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo gpg --dearmor -o /usr/share/keyrings/docker-archive-keyring.gpg

echo "deb [arch=$(dpkg --print-architecture) signed-by=/usr/share/keyrings/docker-archive-keyring.gpg] https://download.docker.com/linux/ubuntu $(lsb_release -cs) stable" | sudo tee /etc/apt/sources.list.d/docker.list > /dev/null

sudo apt update

apt-cache policy docker-ce

sudo apt install docker-ce

sudo systemctl status docker
```

# 3. How To Secure Nginx with Let's Encrypt on Ubuntu 22.04
```sh
sudo snap install core; sudo snap refresh core.

sudo apt remove certbot

sudo snap install --classic certbot

sudo certbot --nginx -d example.com -d www.example.com
```

# 4. Docker command line
```sh
docker rm -f $(docker ps -aq) && docker rmi -f $(docker images -aq) && docker volume rm $(docker volume ls -q)

docker run --name mariadb -e MYSQL_ROOT_PASSWORD=ThongDang79! -p 3306:3306 -d --network=mariadb_network docker.io/library/mariadb

docker exec -it mariadb /bin/bash

docker exec -it mariadb /sh

docker compose up -d

dokcer compose down && docker compose up -d

docker compose -f docker-compose.yaml --env-file /docker/vps/.env up -d
```
