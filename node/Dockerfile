# Seleciona imagem base para montar a imagem personalizada 
FROM node:15

# Seleciona do diretorio de trabalho do container
WORKDIR /usr/src/app

# Prepara para instalação do DOCKERIZE
RUN apt-get update && apt-get install -y wget

# Instala o Dockerize. DOCKERIZE  é um script responsavel por criar ordenação de dependencias garantindo que o node aguarde o db estar ponto
ENV DOCKERIZE_VERSION v0.6.1
RUN wget https://github.com/jwilder/dockerize/releases/download/$DOCKERIZE_VERSION/dockerize-linux-amd64-$DOCKERIZE_VERSION.tar.gz \
    && tar -C /usr/local/bin -xzvf dockerize-linux-amd64-$DOCKERIZE_VERSION.tar.gz \
    && rm dockerize-linux-amd64-$DOCKERIZE_VERSION.tar.gz

# Copia o conteudo da pasta local raiz para pasta raiz do container
COPY . .

# Expõe a porta 3000 do container na network do Docker
EXPOSE 3000