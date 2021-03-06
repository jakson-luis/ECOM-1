# Servidor Wordpress + MariaDB com Docker 
Este repositório contêm scripts e configurações para executar um servidor apache com Wordpress utilizando serviços _Docker_
>Para mais informações sobre docker, consulte: https://aws.amazon.com/pt/docker/

>Para documentação da imagem de Wordpress, consulte: https://hub.docker.com/_/wordpress/

>Para documentação da imagem de MariaDB, consulte: https://hub.docker.com/_/mariadb/
## Instalação Linux (Ubuntu 16.04.3 Xenial)
### Comandos no terminal
#### 1- Baixe ou clone este repositório para sua máquina local.
```
git clone https://github.com/duckiemcduck/ecom/
```
#### 2- Entre no diretório do projeto.
```
cd ecom
```
#### 3- Certifique-se que docker está instalado através deste comando:
```
docker
```

>Se não estiver, execute o script de instalação. Requer permissão de super-usuário.
```
./install-docker.sh
```

#### 4- Certifique-se que docker-compose está instalado através deste comando:
```
docker-compose
```

>Se não estiver, execute o script de instalação. Requer permissão de super-usuário.
```
./install-docker-compose.sh
```

#### 5- Identifique a porta que você deseja para o serviço Wordpress.

Por padrão, o serviço irá alocar a porta `80` em `localhost`. Isto pode ser alterado [nesta linha de docker-compose.yml](https://github.com/duckiemcduck/ECOM/blob/master/docker-compose.yml#L11&L12)

---
[Arquivo docker-compose.yml](https://github.com/duckiemcduck/ECOM/blob/master/docker-compose.yml#L11&L12)
```
ports:
 - 80:80
```
  >Serviço responderá em http://localhost
```
ports:
 - 8080:80
```
  >Serviço responderá em http://localhost:8080
---

#### 6- Execute o serviço

```
sudo docker-compose up
```

#### 7- Identifique o endereço alocado pelo servidor.

*Os processos do banco de dados e do servidor serão iniciados.*

O processo do servidor esperará o processo do banco de dados inicializar antes de alocar um endereço.
![http://i.imgur.com/etxmjAj.png](http://i.imgur.com/etxmjAj.png)

#### 8- Acesse o endereço pelo navegador e configure Wordpress como desejar.
![http://i.imgur.com/8lDLo9h.png](http://i.imgur.com/8lDLo9h.png)
 --
 
 ## Entrando no Banco de Dados
 #### 1- Para entrar no container do banco de dados, digite:
 ```
 sudo docker exec -i -t ecom_mariadb_1 /bin/bash
 ```
 #### 2- Entre no banco. A senha e o nome do banco de dados são fornecidos no arquivo docker-compose.yml.
 ```
 mysql -u root -p wordpress
 senha admin
 ```
 
 
