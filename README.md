# Hackaton Orbitall 2025 - API de Gestão de Clientes e Transações

API REST desenvolvida como solução para o desafio final do Hackaton Orbitall 2025, focada no gerenciamento de clientes e suas transações financeiras.

## 🚀 Tecnologias Utilizadas
- Java 21
- Spring Boot 3.5.6
- Spring Data JPA
- Spring Web
- Spring Validation
- H2 Database (banco de dados em memória)
- Lombok
- Maven

## ⚙️ Pré-requisitos
- JDK 21 ou superior
- Apache Maven 3.8+

## ▶️ Como Rodar a Aplicação

1. **Clone o repositório:**
   ```bash
   git clone [URL_DO_SEU_REPOSITORIO]
   cd HackatonOrbitall2025
   ```

2. **Compile e instale as dependências com o Maven:**
   ```bash
   mvn clean install
   ```

3. **Execute a aplicação:**
   ```bash
   mvn spring-boot:run
   ```
A aplicação estará rodando em `http://localhost:8080`.

## 🗄️ Acessando o Banco de Dados (H2 Console)

Com a aplicação em execução, é possível acessar o console do banco de dados em memória H2 para visualizar as tabelas (`CUSTOMERS`, `TRANSACTIONS`) e executar queries SQL.

1.  Acesse a URL: [**http://localhost:8080/h2-console**](http://localhost:8080/h2-console)

2.  Utilize as seguintes credenciais na tela de login:
    * **Driver Class:** `org.h2.Driver`
    * **JDBC URL:** `jdbc:h2:mem:hackatondb`
    * **User Name:** `sa`
    * **Password:** (deixe em branco)

**Atenção:** É fundamental que o campo `JDBC URL` seja preenchido exatamente como acima para conectar-se à mesma instância de banco de dados que a aplicação está utilizando.

## 📡 Endpoints e Exemplos de Uso

A seguir estão exemplos de requisições que podem ser feitas com `curl` ou no Postman.

### Clientes (`/customers`)

**1. Cadastrar um novo cliente (POST)**
```bash
curl -X POST http://localhost:8080/customers \
-H "Content-Type: application/json" \
-d '{
    "fullName": "Sérgio Sampaio",
    "email": "sergio.sampaio@orbitall.com",
    "phone": "11987654321"
}'
```

**2. Buscar cliente por ID (GET)**
```bash
curl http://localhost:8080/customers/{customerId}
```

**3. Listar todos os clientes ativos (GET)**
```bash
curl http://localhost:8080/customers
```

### Transações (`/transactions`)

**1. Criar uma nova transação (POST)**
```bash
curl -X POST http://localhost:8080/transactions \
-H "Content-Type: application/json" \
-d '{
    "customerId": "ID_DO_CLIENTE_EXISTENTE",
    "amount": 199.99,
    "cardType": "CREDITO"
}'
```

**2. Listar transações de um cliente (GET)**
```bash
curl http://localhost:8080/transactions?customerId={customerId}
```
---
