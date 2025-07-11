# Discovery Service

## Descrição

Este projeto é um serviço de descoberta de instâncias de APIs utilizando Spring Cloud Netflix Eureka Server. Em uma
arquitetura de microsserviços, o Discovery Service é responsável por manter um registro de todas as instâncias de
serviços disponíveis, permitindo que os serviços se encontrem e se comuniquem dinamicamente.

## Funcionalidades

- **Registro de Serviços:** Microsserviços podem se registrar no Eureka Server para se tornarem visíveis para outros
  serviços.
- **Descoberta de Serviços:** Microsserviços podem consultar o Eureka Server para obter a localização de outros
  serviços.
- **Monitoramento de Saúde:** O Eureka Server monitora a saúde das instâncias de serviço registradas.

## Tecnologias Utilizadas

- **Java 17**
- **Spring Boot 3.3.5**
- **Spring Cloud Netflix Eureka Server**
- **Maven**
- **Docker**

## Como Executar

### Pré-requisitos

- Java 17 ou superior
- Maven 3.x
- Docker

### Executando Localmente

1. Clone o repositório:
   ```bash
   git clone https://github.com/seu-usuario/discovery.git
   ```
2. Navegue até o diretório do projeto:
   ```bash
   cd discovery
   ```
3. Execute a aplicação:
   ```bash
   mvn spring-boot:run
   ```

A aplicação estará disponível em `http://localhost:8761`.

### Executando com Docker

1. Construa a imagem Docker:
   ```bash
   docker build -t discovery .
   ```
2. Execute o container:
   ```bash
   docker run -p 8761:8761 discovery
   ```

## CI/CD

O projeto possui um pipeline de CI/CD configurado com GitHub Actions. O pipeline é acionado por pushes na branch `main`
e executa as seguintes etapas:

1. **Build:** Compila o projeto.
2. **Testes:** Executa os testes unitários.
3. **Deploy:** Constrói a imagem Docker e a envia para o Docker Hub.
4. **Versionamento:** Incrementa a versão do projeto no `pom.xml`.
