# Docker
Docker installation:
https://docs.docker.com/engine/install/ubuntu/

apt-get update
 
 
apt-get install \
    apt-transport-https \
    ca-certificates \
    curl \
    gnupg \
    lsb-release
 
 
curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo gpg --dearmor -o /usr/share/keyrings/docker-archive-keyring.gpg
 
 
echo \
  "deb [arch=amd64 signed-by=/usr/share/keyrings/docker-archive-keyring.gpg] https://download.docker.com/linux/ubuntu \
  $(lsb_release -cs) stable" | sudo tee /etc/apt/sources.list.d/docker.list > /dev/null
 
 
apt-get update
apt-get install docker-ce docker-ce-cli containerd.io
 
systemctl status docker
docker info

Document - HealtCheck Document Resource
Documentation Referred:

https://docs.docker.com/engine/reference/builder/

https://docs.docker.com/engine/reference/run/#healthcheck

Code Used:

docker run -dt --name tmp  --health-cmd "curl --fail http://localhost" --health-interval=5s busybox sh
 
docker run -dt --name tmp2 --health-cmd "curl -f http://localhost" --health-interval=5s --health-retries=1 busybox sh
 
curl  http://dexter.kplabs.in/test
 
curl -f http://dexter.kplabs.in/test214.txt
