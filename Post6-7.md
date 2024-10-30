# Aula 06 - Chatbots com base de conhecimento - Dify

Nesta aula, instalei e configurei o Dify, um chatbot com base de conhecimento, além de instalar o N8n para automações adicionais. Abaixo está o passo a passo de como fiz isso.

## Instalação do Dify

### Clonando o repositório

Primeiro, clonei o repositório do Dify do GitHub e naveguei até a pasta correta:

```bash
git clone https://github.com/langgenius/dify.git
cd dify/docker
```

### Configurando o ENV e a porta do NGINX

Depois, criei uma cópia do arquivo `.env.example` e fiz algumas alterações, como definir uma senha para o usuário administrador e alterar a porta exposta do NGINX para 8080:

```bash
cp .env.example .env
# Configurando a senha de inicialização do usuário admin.
INIT_PASSWORD=sk-9f73s3ljTX
# Alterando a porta exposta do NGINX.
EXPOSE_NGINX_PORT=8080
```

### Executando o Docker Compose

Com as configurações feitas, executei o comando para subir os contêineres:

```bash
docker compose up -d
```

### Atualizando o Dify

Se fosse necessário atualizar o Dify, usei os seguintes comandos:

```bash
cd dify/docker
docker compose down
git pull origin main
docker compose pull
docker compose up -d
```

## Introdução ao Dify

Apos instalar, explorei as funcionalidades do Dify, que permite a criação de chatbots inteligentes com base em uma vasta base de conhecimento.

## Instalação do N8n

Para integração e automação, instalei o N8n, seguindo os passos abaixo:

### Criando a pasta para o N8n

Primeiro, criei uma pasta dedicada para o N8n e entrei nela:

```bash
mkdir n8n
cd n8n/
```

### Criando o arquivo Docker Compose

Depois, criei o arquivo `docker-compose.yaml` com a seguinte configuração:

```yaml
version: "3.2"
services:
  n8n:
    image: n8nio/n8n
    ports:
      - "5678:5678"
    environment:
      - N8N_BASIC_AUTH_USER=admin
      - N8N_BASIC_AUTH_PASSWORD=8H4a10032024
    volumes:
      - n8n_data:/home/node/.n8n
    networks:
      - n8n-net

volumes:
  n8n_data:

networks:
  n8n-net:
    name: n8n-net
    driver: bridge
```

<contexto>
Seu nome é Clara, você trabalha na Concecionaria Auto Carros.
Se apresente no início da conversa.

Você deve orientar o usuário a encontrar o carro ideal.
</contexto>


<etapas>
1. Solicite o nome do usuário
2. Pergunte para que tipo de uso será o carro
3. Faça poucas perguntas para identificar o carro ideal para o cliente
4. Sugira um carro ou uma lista de carros com base no perfil dele. Utilize a ferramenta {crawl} para encontrar imagens dos carros e enviar para ele.
5. Assim que o usuário escolher o carro, agradeça e diga que irá encaminhá-lo para o Gerente Caetano, que irá agendar um teste Drive.
</etapas> 


<response_format>
Responda o usuário cordiamente e Não responda perguntas fora do contexto.
</response_format> 
```

Ferramentas: Crawl Search.



