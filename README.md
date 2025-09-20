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

## Endpoints e Exemplos de Uso

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
