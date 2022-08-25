# Instruções para criar a imagem do docker do ambiente de desenvolvimento

## Primeiro passo 
Instale o docker, git e docker-compose em seu computador

Links: 
https://www.docker.com/get-started

https://git-scm.com/

## Segundo passo 
Abra o terminal e clone o respostório em alguma pasta local

````
git clone https://github.com/vascmig/container_rails_ACH2006.git
````

## Terceiro passo 
Entre no repositorio clonado e crie o esqueleto do projeto rails

````
docker compose run --no-deps web rails new . --force --no-deps 
````

## Quarto passo 

Construa a imagem do container docker

````
docker compose build
````

## Quinto passo 
Inicie a execução do container

````
docker compose up
````

## Sexto passo 
Execute os comandos, dentro do mesmo diretório do projeto (em outro terminal, ou seja, não feche o terminal que está rodando o programa do docker)

````
docker compose exec web rails generate rspec:install
docker compose exec web rails generate cucumber:install
````

## Sétimo passo 
Para validar se tudo foi executado corretamente, teste os seguintes comandos:

````
docker compose exec web rake spec
docker compose exec web rake cucumber
````

## Observação
Para executar comandos específicos dentro do container, execute o seguinte comando: 

````
docker compose exec web comando
````

Por exemplo:

````
docker compose exec web rails routes
````

## POSSÍVEIS ERROS 
É possível que o git mude as quebras de linha de Linux para Windows, o que ocasionará um erro ao seguir o tutorial. Neste caso, certifique-se de que TODOS os arquivos utilizados utilizem a terminação de linha LF em vez de CRLF.

# Para dúvidas

Por favor, em caso de dúvidas postar no fórum online do e-disciplinas
