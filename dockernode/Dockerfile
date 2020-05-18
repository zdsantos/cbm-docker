ARG VERSION=alpine

# - define a imagem base sobre a qual estamos buildando
# - é a primeira instrução e só pode ser precedida das instruções ARGs
# - usando a versão alpine que é uma versão reduzida só com a parte do SO
FROM node:${VERSION}

# - diretorio na "maquina" docker
WORKDIR /usr/app

# - copiar os arquivos para o WORKDIR
COPY package*.json ./
RUN npm install

COPY . .

# - define a porta que o servidor deve expor
# - pode definir o protocolo de acesso usando <port>/<protocol>, ex: 3000/tcp
EXPOSE 3000

# - unico por Dockerfile
# - comando que starta a aplicação
# - se houver mais de um, só o último é executado
CMD [ "npm", "start" ]

# - comando para rodar o docker
# $ docker build -t cbm/dockernode .
#
# esse comando executa o Dockerfile para montar a imagem docker
#
# para rodar a aplicação
# $ docker run -p 3000:3000 -d cbm/dockernode
#
# -p port_local/port_docker
# -d nome da imagem