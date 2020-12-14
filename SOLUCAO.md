# Solução do Trabalho

![Docker Image CI Client](https://github.com/devsalula/Trabalho-Individual-2020-1/workflows/Docker%20Image%20CI%20Client/badge.svg)
![Docker Image CI](https://github.com/devsalula/Trabalho-Individual-2020-1/workflows/Docker%20Image%20CI/badge.svg)

[![Quality Gate Status](https://sonarcloud.io/api/project_badges/measure?project=devsalula_Trabalho-Individual-2020-1&metric=alert_status)](https://sonarcloud.io/dashboard?id=devsalula_Trabalho-Individual-2020-1)
[![Maintainability Rating](https://sonarcloud.io/api/project_badges/measure?project=devsalula_Trabalho-Individual-2020-1&metric=sqale_rating)](https://sonarcloud.io/dashboard?id=devsalula_Trabalho-Individual-2020-1)

Para atender a demanda do trabalho, dockerização da API e do Front End e a pipeline utilizando o Github Actions das duas camadas.

## Dockerização

Para a Dockerização foi utilizado um `docker-compose` na api, devido a necessidade de subir o container do Banco de dados.

Para poder rodar a API vá até o seu diretório, comece rodando os seguintes comandos:

```
docker-compose build
```
- Para poder criar um build novo da api

### Caso esteja rodando pela primeira vez, rode o seguinte comando:
```
docker-compose run api rails db:create db:migrate
```
- Para poder criar e fazer a migração do banco de dados

### Para rodar a API defitivamente:
```
docker-compose up
```
- Assim você irá colocar a api e o banco de dados para rodar.

### Front End

Para poder rodar o Front End vá até o seu diretório, basta rodar:

```
docker build -t client .
```
- Cria um build do Front end

```
docker run -it -p 8080:8080 client
```
- Roda o Front End


## Pipeline

Na Integração Contínua foi utilizado o Github Actions.

Como o projeto é um monorepo, foi criado duas pipelines, uma para o back e outra para o front, onde elas só são executadas, caso ocorra uma alteração no seu diretório, ou seja a análise ocorre individualmente.

A Pipeline para o Back se chama - `Docker Image CI`

A Pipeline para o Front se chama - `Docker Image CI Client`