# Solução do Trabalho

Para poder rodar a API, comece rodando os seguintes comandos:

```
docker-compose build
```
- Para poder criar um build novo da api e do banco de dados

Caso esteja rodando pela primeira vez, rode o seguinte comando:
```
docker-compose run api rails db:create db:migrate
```
- Para poder criar e fazer a migração do banco de dados

Para rodar a API defitivamente:
```
docker-compose up
```
- Assim a API roda por completo, podendo receber requisições.

Para poder rodar o Front End, basta rodar:

```
docker build -t client .
```
- Cria um build do Front end

```
docker run -it -p 8080:8080 client
```
- Roda o Front End

# Trabalho Individual - GCES - 2020/1

A Gestão de Configuração de Software é parte fundamental no curso de GCES, e dominar os conhecimentos de configuração de ambiente, containerização, virtualização, integração e deploy contínuo tem se tornado cada vez mais necessário para ingressar no mercado de trabalho.

Para exercitar estes conhecimentos, você deverá aplicar os conceitos estudados ao longo da disciplina no produto de software contido neste repositório.

O sistema se trata de uma aplicação Web, cuja funcionalidade consiste na pesquisa e exibição de perfis de usuários do GitHub, que é composta de:

- Front End escrito em Javascript, utilizando os frameworks Vue.JS e Quasar;
- Back End escrito em Ruby on Rails, utilizado em modo API;
- Banco de Dados PostgreSQL;

Para executar a aplicação na sua máquina, basta seguir o passo-a-passo descrito no arquivo [Descrição e Instruções](Descricao-e-Instrucoes.md).

## Critérios de avaliação

### 1. Containerização

A aplicação deverá ter seu ambiente completamente containerizado. Desta forma, cada subsistema (Front End, Back End e Banco de Dados) deverá ser isolado em um container individual.

Deverá ser utilizado um orquestrador para gerenciar comunicação entre os containers, o uso de credenciais, networks, volumes, entre outras configurações necessárias para a correta execução da aplicação.

Para realizar esta parte do trabalho, recomenda-se a utilização das ferramentas:

- Docker versão 17.04.0+
- Docker Compose com sintaxe na versão 3.2+

### 2. Integração contínua

Você deverá criar um 'Fork' deste repositório, onde será desenvolvida sua solução. Nele, cada commit submetido deverá passar por um sistema de integração contínua, realizando os seguintes estágios:

- Build: Construção completa do ambiente;
- Testes: Os testes automatizados da aplicação devem ser executados;
- Coleta de métricas: Deverá ser realizada a integração com algum serviço externo de coleta de métricas de qualidade;

O sistema de integração contínua deve exibir as informações de cada pipeline, e impedir que trechos de código que não passem corretamente por todo o processo sejam adicionados à 'branch default' do repositório.

Para esta parte do trabalho, poderá ser utilizada qualquer tecnologia ou ferramenta que o aluno desejar, como GitlabCI, TravisCI, CircleCI, Jenkins, CodeClimate, entre outras.

### 3. Deploy contínuo (Extra)

Caso cumpra todos os requisitos descritos acima, será atribuída uma pontuação extra para o aluno que configure sua pipeline de modo a publicar a aplicação automaticamente, sempre que um novo trecho de código seja integrado à branch default.
