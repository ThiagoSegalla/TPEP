

## Baixar as Ferramentas

### 1. Baixar LLM Studio

Para baixar e iniciar o LLM Studio com Docker, utilize o comando a seguir:

```bash
# Clone o repositório
git clone https://github.com/<repositório-llm-studio>.git

# Navegue até a pasta do projeto
cd llm-studio

# Execute o Dockerfile fornecido no repositório
docker build -t llm-studio .

docker run -p 8080:8080 -v /path/to/data:/app/data llm-studio
```

### 2. Baixar Anything LLM

Para instalar Anything LLM:

```bash
# Clone o repositório
git clone https://github.com/<repositório-anything-llm>.git

# Navegue até a pasta do projeto
cd anything-llm

# Execute o Dockerfile fornecido no repositório
docker build -t anything-llm .

docker run -p 8000:8000 -v /path/to/data:/app/data anything-llm
```

### 3. Baixar Ollama

Para baixar Ollama:

```bash
# Clone o repositório
git clone https://github.com/<repositório-ollama>.git

# Navegue até a pasta do projeto
cd ollama

# Execute o Dockerfile fornecido no repositório
docker build -t ollama .

docker run -p 5000:5000 -v /path/to/data:/app/data ollama
```

## Baixar Modelos

Para baixar modelos e salvá-los na pasta correta, siga o exemplo abaixo:

1. Crie a pasta para armazenar os modelos:

```bash
mkdir -p C:\Users\<SEU_USUARIO>\.cache\lm-studio\models
```

2. Baixe os modelos desejados e salve-os na pasta criada:

```bash
# Exemplo para baixar um modelo
wget -P C:\Users\<SEU_USUARIO>\.cache\lm-studio\models <link_do_modelo>
```

Altere o caminho conforme a necessidade para apontar ao seu diretório local.

