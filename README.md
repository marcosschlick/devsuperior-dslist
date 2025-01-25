# **DSList - Backend**

Este é o repositório do projeto **DSList**, uma API RESTful desenvolvida em **Java Spring Boot** durante o **Intensivão Java Spring** da **DevSuperior**, sob orientação do professor **Nelio Alves**. A API gerencia listas de jogos com funcionalidades como movimentação de jogos entre posições, consultas personalizadas e integração com banco de dados.

---

## **Funcionalidades**

- **Listagem de jogos**: Busca todos os jogos ou um jogo específico por ID.
- **Listagem de listas de jogos**: Recupera todas as listas de jogos disponíveis.
- **Busca de jogos por lista**: Retorna os jogos de uma lista específica, ordenados por posição.
- **Movimentação de jogos**: Permite mover um jogo de uma posição para outra dentro de uma lista.
- **Integração com banco de dados**: Utiliza **PostgreSQL** para produção e **H2** para testes.

---

## **Tecnologias Utilizadas**

- **Linguagem**: Java
- **Framework**: Spring Boot
- **Banco de Dados**: PostgreSQL (produção) e H2 (testes)
- **Ferramentas**:
  - Docker (para configuração do ambiente com PostgreSQL e pgAdmin)
  - Railway (para deploy na nuvem)
  - Postman (para testes de requisições HTTP)

---

## **Recursos Incluídos**

- **Collection do Postman**: Arquivo `DSList.postman_collection.json` com todas as requisições para testar a API.
- **Docker Compose**: Arquivo `docker-compose.yml` para configurar o ambiente com PostgreSQL e pgAdmin.
- **Script de Criação do Banco de Dados**: Arquivo `create.sql` com o script SQL para criar as tabelas e popular o banco de dados.

---

## **Estrutura do Projeto**

O projeto segue o padrão de camadas:
1. **Controladores REST**: Gerenciam as requisições HTTP e respostas.
2. **Serviços**: Implementam as regras de negócio.
3. **Repositórios**: Responsáveis pelo acesso ao banco de dados.
4. **DTOs (Data Transfer Objects)**: Utilizados para transferir dados entre as camadas.

---

## **Modelo de Domínio**

![Modelo de domínio DSList](https://raw.githubusercontent.com/devsuperior/java-spring-dslist/main/resources/dslist-model.png)

---

## **Configuração do Ambiente**

### **Banco de Dados**

- **H2**: Banco de dados em memória para testes. Acessível via `/h2-console`.
- **PostgreSQL**: Banco de dados principal para produção. Configurado via Docker ou na nuvem (Railway).

### **Arquivos de Configuração**

- **`application-dev.properties`**: Configurações para o ambiente de desenvolvimento.
- **`application-prod.properties`**: Configurações para o ambiente de produção.
- **`application-test.properties`**: Configurações para o ambiente de testes.

### **Docker**

Para configurar o ambiente com Docker, utilize o arquivo `docker-compose.yml` disponível no repositório.

---

## **Endpoints Principais**

- **GET /games**: Retorna todos os jogos.
- **GET /games/{id}**: Retorna um jogo específico por ID.
- **GET /lists**: Retorna todas as listas de jogos.
- **GET /lists/{listId}/games**: Retorna os jogos de uma lista específica.
- **POST /lists/{listId}/replacement**: Move um jogo de uma posição para outra dentro de uma lista.

---

## **Como Executar o Projeto**

1. Clone o repositório:
   ```bash
   git clone https://github.com/marcosschlick/devsuperior-dslist.git
   ```
2. Configure o banco de dados:
   - Para desenvolvimento: Utilize o H2 ou configure o PostgreSQL localmente.
   - Para produção: Configure as variáveis de ambiente no arquivo `application-prod.properties`.
3. Execute o projeto:
   ```bash
   ./mvnw spring-boot:run
   ```
4. Acesse os endpoints via Postman ou navegador.

---

## **Testando a API com Postman**

- Importe a collection `DSList.postman_collection.json` no Postman.
- Execute as requisições para testar todos os endpoints da API.

---

## **Configuração do Ambiente com Docker**

1. Execute o comando abaixo para subir os contêineres do PostgreSQL e pgAdmin:
   ```bash
   docker-compose up -d
   ```
2. Acesse o pgAdmin em `http://localhost:5050` e configure a conexão com o PostgreSQL.

---

## **Criação do Banco de Dados**

- Utilize o script `create.sql` para criar as tabelas e popular o banco de dados com dados iniciais.
- Execute o script no PostgreSQL ou no H2, dependendo do ambiente.

---

## **Desafios Futuros**

- Desenvolver o frontend para consumir essa API, utilizando tecnologias como **ReactJS** ou **Angular**.
- Implementar autenticação e autorização para proteger os endpoints.
- Adicionar testes automatizados (unitários e de integração).
- Explorar práticas de CI/CD para automatizar o deploy.
