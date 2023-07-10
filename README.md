# expert-barnacle
Dicas

######### DOCKER ######################################################################################################################################################

sudo apt-get update

sudo apt-get install \
    ca-certificates \
    curl \
    gnupg \
    lsb-release
    
sudo mkdir -p /etc/apt/keyrings

curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo gpg --dearmor -o /etc/apt/keyrings/docker.gpg

echo \
  "deb [arch=$(dpkg --print-architecture) signed-by=/etc/apt/keyrings/docker.gpg] https://download.docker.com/linux/ubuntu \
  $(lsb_release -cs) stable" | sudo tee /etc/apt/sources.list.d/docker.list > /dev/null
  
sudo apt-get update

sudo apt-get install docker-ce docker-ce-cli containerd.io docker-compose-plugin

sudo docker run hello-world

sudo groupadd docker

sudo usermod -aG docker $USER

newgrp docker

docker run hello-world

######### DOCKER-COMPOSE ##############################################################################################################################################

sudo curl -L "https://github.com/docker/compose/releases/download/v2.12.2/docker-compose-$(uname -s)-$(uname -m)" -o /usr/local/bin/docker-compose

sudo chmod +x /usr/local/bin/docker-compose

docker-compose --version

######### GIT #########################################################################################################################################################

git config --global user.name ""

git config --global user.email ""

ssh-keygen -t rsa -b 4096 -C ""

eval "$(ssh-agent -s)"

ssh-add ~/.ssh/id_rsa

cat ~/.ssh/id_rsa.pub

######### WSL 2 no Windows 10 #########################################################################################################################################

### Passo 1 (PowerShell Admin): 
dism.exe /online /enable-feature /featurename:Microsoft-Windows-Subsystem-Linux /all /norestart

### Passo 2 (PowerShell Admin):
dism.exe /online /enable-feature /featurename:VirtualMachinePlatform /all /norestart

### Passo 3
REINICIE O COMPUTADOR

### Passo 4 (Download the Linux kernel update package):
https://wslstorestorage.blob.core.windows.net/wslblob/wsl_update_x64.msi

### Passo 5 (PowerShell Admin):
wsl --set-default-version 2

### Passo 6 (Instale a versao desejada do Ubuntu na Microsoft Store)

### Passo 7 (Atualize a maquina)
sudo apt dist-upgrade

### Passo 8 (Instale o Docker)
seguir os passos da documentação oficial do docker, pois ela sempre é atualizada!
https://docs.docker.com/engine/install/ubuntu/

sudo usermod -aG docker $USER

sudo service docker start

sudo update-alternatives --config iptables
e escolha a opção 1 iptables-legacy

sudo service docker start

docker ps
