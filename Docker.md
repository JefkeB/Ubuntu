

# Docker install
As Docker does not support Ubuntu 19.10 at this moment we are using the version for 19.04.  
  
    
Add GPG key for the official Docker repo
```
curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo apt-key add -
```
   
Add Docker repo to apt
```
sudo bash -c 'echo "deb [arch=amd64] https://download.docker.com/linux/ubuntu disco stable" > /etc/apt/sources.list.d/docker-ce.list'
```

Update apt database
```
sudo apt-get update
```

We must use the install from the Dcoker repo and not the default one from Ubunut 19.10
```
aptc-cache policy docker-ce
```

Install Docker
```
sudo apt-get install -y docker-ce
```

Verify docker daemon is started
```
sudo systemctl status docker
```

When Docker is run root privileges are required, to run Docker without typing sudo execute the following steps.  
Add your username to the *docker* group  
```
sudo usermod -aG docker ${USER}
```
Type following to enter the new group
```
su ${USER}
```
The user's password will be asked to continue    
View if added  
```
id -nG
```

Test by running hello world
```
docker run hello-world
```
