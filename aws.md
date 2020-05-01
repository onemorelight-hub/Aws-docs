## Install doccker 

sudo yum install -y docker

# Install docker compose 
## change to super user

sudo su

sudo curl -L https://github.com/docker/compose/releases/download/1.20.0/docker-compose-`uname -s`-`uname -m` -o /usr/local/bin/docker-compose

sudo chmod +x /usr/local/bin/docker-compose

## change to basic user 

exit

##

netstat -tulpn | grep LISTEN 

##### ERROR ####

####If you want to run docker as non-root user then you need to add it to the docker group.

#####Create the docker group if it does not exist
$ sudo groupadd docker

####Add your user to the docker group.
$ sudo usermod -aG docker $USER

#####Run the following command or Logout and login again and run (that doesn't work you may need to reboot your machine first)
$ newgrp docker

#####Check if docker can be run without root
$ docker run hello-world
#####Taken from the docker official documentation: manage-docker-as-a-non-root-user
