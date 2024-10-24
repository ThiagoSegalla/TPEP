

### wsl --update

Definir a versão 2 do WSL como padrão

wsl --set-default-version 2

### Instalar o Ubuntu


wsl --install

**Foi necessário habilitar o WSL nos recursos do Windows e reiniciar o computador para seguir**

wsl -l -o

### Instalando o Docker no Ubuntu

Configuração do repositório apt do Docker

1. Adicione a chave GPG oficial do Docker:

    sudo apt-get update
    sudo apt-get install ca-certificates curl
    sudo install -m 0755 -d /etc/apt/keyrings
    sudo curl -fsSL https://download.docker.com/linux/ubuntu/gpg -o /etc/apt/keyrings/docker.asc
    sudo chmod a+r /etc/apt/keyrings/docker.asc

2. Adicione o repositório do Docker às fontes do apt:

    echo \
    "deb [arch=$(dpkg --print-architecture) signed-by=/etc/apt/keyrings/docker.asc] https://download.docker.com/linux/ubuntu \
    $(. /etc/os-release && echo "$VERSION_CODENAME") stable" | \
    sudo tee /etc/apt/sources.list.d/docker.list > /dev/null
    sudo apt-get update

Instalação dos pacotes do Docker
Para instalar a versão mais recente do Docker, execute:

sudo apt-get install docker-ce docker-ce-cli containerd.io docker-buildx-plugin docker-compose-plugin

Verificando a instalação do Docker
Para confirmar que o Docker foi instalado corretamente, execute o comando a seguir, que irá rodar a imagem hello-world:

sudo docker run hello-world
