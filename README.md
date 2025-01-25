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

## **Desafios Futuros**

- Desenvolver o frontend para consumir essa API, utilizando tecnologias como **ReactJS** ou **Angular**.
- Implementar autenticação e autorização para proteger os endpoints.
- Adicionar testes automatizados (unitários e de integração).
- Explorar práticas de CI/CD para automatizar o deploy.
