#  LAMP stack built with Docker Compose

![Landing Page](https://preview.ibb.co/gOTa0y/LAMP_STACK.png)

Um ambiente básico de pilha LAMP criado usando o Docker Compose. Consiste no seguinte:
* PHP
* Apache
* MySQL
* phpMyAdmin
* Redis

A partir de agora, temos várias versões diferentes do PHP. Use a versão php apropriada conforme necessário:

* 5.4.x
* 5.6.x
* 7.1.x
* 7.2.x
* 7.3.x
* 7.4.x

> Observe que simplificamos a estrutura do projeto de várias ramificações para cada versão php, para uma ramificação mestre centralizada. 

##  Instalação 
* Crie uma conta no Docker HUB 
  https://www.docker.com/get-started 
* Baixe o docker desktop do repositório oficial e instale.
  https://www.docker.com/get-started
* Clone este repositório no seu computador local 
```shell
git clone https://github.com/cheerokee/docker-lampp.git 
cd docker-lampp/
```
* Pare qualquer serviço que esteja executando na porta 80, 
ou altere a porta do container webserver dentro do arquivo 
docker-compose.yml 
* Crie um arquivo .env a partir do arquivo sample.env e 
  altere informações como exemplo a versão do PHP a seu gosto.
* Clone outros projeto dentro da pasta www/html, de forma que fique: 
Ex. www/html/projeto1, www/html/projeto2, etc.
* Crie Vhosts no arquivo config/vhots/default.conf lembrando que seus projetos estarão localizados 
  na pasta /var/www/html no container.
* Adicionar host na sua maquina local no arquivo hosts:
Ex: 127.0.0.1 exemplo.dev.br 

* Acesse a pasta raiz do diretorio docker onde se encontra o arquivo 
  docker-compose.yml e execute o comando no terminal: `docker-compose up -d`.
  
Obs: Para qualquer alteração no arquivo docker-compose.yml ou 
.env execute o comando acima com o acrescimo da flag --build. 
`docker-compose up -d -- build`

Você pode acessar o shell do container como se realmente 
estivesse em um servidor linux com o seguinte comando: 
`docker-compose exec webserver bash` e digite `exit` para sair do terminal do container.

Para mais informações acesse o repositório original: 
https://github.com/sprintcube/docker-compose-lamp
