#Configurando o arquivo Dockerfile:

# Use uma imagem base do Nginx
FROM nginx

# Remova o arquivo padrão do Nginx "SE NECESSÁRIO"
RUN rm /usr/share/nginx/html/*

# Copie todo o conteúdo da pasta do seu projeto para o diretório padrão do Nginx no contêiner
COPY . /usr/share/nginx/html

# Exponha a porta 80 (a porta padrão do Nginx)
EXPOSE 80

# Comando para iniciar o servidor Nginx
CMD ["nginx", "-g", "daemon off;"]



# No CMD/Shell
Rodar o comando, para construir uma imagem Docker, isso criará uma imagem Docker com o nome "meu-aplicativo-html" a partir do Dockerfile no diretório atual:
docker build -t meu-aplicativo-html .

#Após, executar o comando:
docker run -d -p 8080:80 meu-aplicativo-html

#Isso executará o contêiner em segundo plano e mapeará a porta 8080 do host para a porta 80 do contêiner, onde o servidor Nginx está servindo sua aplicação HTML.
Agora você pode acessar a sua aplicação HTML em um navegador da web, indo para http://localhost:8080 no seu computador.
