# 🧪 Teste Técnico – Estágio em APIs (.NET)

## 📌 Objetivo

O objetivo deste teste é avaliar seus conhecimentos em:

* Lógica de programação
* Orientação a Objetos
* C# e ASP.NET Core
* Entity Framework Core
* Organização de código

---

## 🚀 Desafio

Você deverá desenvolver uma **API REST em .NET** para gerenciamento de pedidos.

---

## 🧰 Tecnologias esperadas

* .NET (versão 9 ou superior)
* ASP.NET Core Web API
* Entity Framework Core
* SQL Server (via Docker – já fornecido)

---

## 🐳 Banco de Dados

Utilize o `docker-compose.yml` fornecido para subir o SQL Server.

---

## 📦 Entidades

### Cliente (Customer)

* Id
* Nome
* Email

### Produto (Product)

* Id
* Nome
* Preço
* Estoque

### Pedido (Order)

* Id
* Data
* ClienteId
* Lista de itens

### Item do Pedido (OrderItem)

* Id
* OrderId
* ProductId
* Quantidade
* PreçoUnitário (no momento da compra)

---

## ⚙️ Regras de Negócio

Sua aplicação deve respeitar as seguintes regras:

1. Não permitir criar um pedido com produtos sem estoque suficiente
2. O preço do produto deve ser armazenado no momento da compra
3. Ao criar um pedido, o estoque do produto deve ser atualizado
4. Não permitir pedidos sem itens
5. O total do pedido deve ser calculado corretamente

---

## 🔌 Endpoints mínimos

### Clientes

* `POST /customers`
* `GET /customers`

### Produtos

* `POST /products`
* `GET /products`

### Pedidos

* `POST /orders`
* `GET /orders`
* `GET /orders/{id}`

---

## 📥 Exemplos de Payloads

### 🧑 Criar Cliente

**POST /customers**

```json
{
  "name": "João Silva",
  "email": "joao@email.com"
}
```

---

### 📦 Criar Produto

**POST /products**

```json
{
  "name": "Notebook",
  "price": 3500.00,
  "stock": 10
}
```

---

### 🧾 Criar Pedido

**POST /orders**

```json
{
  "customerId": 1,
  "items": [
    {
      "productId": 1,
      "quantity": 2
    },
    {
      "productId": 2,
      "quantity": 1
    }
  ]
}
```

---

## 📤 Exemplos de Resposta

### 📦 Produto

```json
{
  "id": 1,
  "name": "Notebook",
  "price": 3500.00,
  "stock": 8
}
```

---

### 🧾 Pedido

```json
{
  "id": 1,
  "date": "2026-04-02T14:30:00",
  "customerId": 1,
  "total": 10500.00,
  "items": [
    {
      "productId": 1,
      "quantity": 2,
      "unitPrice": 3500.00
    }
  ]
}
```

---

## ⚠️ Possíveis Erros Esperados

### ❌ Produto sem estoque suficiente

```json
{
  "error": "Produto sem estoque suficiente"
}
```

---

### ❌ Pedido sem itens

```json
{
  "error": "O pedido deve conter pelo menos um item"
}
```

---

## 📌 Requisitos

* Utilizar Entity Framework Core
* Persistir dados no SQL Server
* Estruturar o projeto de forma organizada
* Código deve ser legível e bem nomeado

---

## 📎 Diferenciais (não obrigatórios)

* Uso de DTOs
* Uso de async/await
* Validações mais robustas, recomendação usar FluentValidation
* Logs básicos
* Migrations do Entity Framework

---

## 📦 Entrega

Você deve entregar:

* Repositório no GitHub
* README com instruções para rodar o projeto
* Passos para rodar o banco e a aplicação

---

## ▶️ Como rodar (esperado)

Explique no seu README:

1. Como subir o banco com Docker
2. Como configurar a string de conexão
3. Como rodar a aplicação

---

## 💬 Observações

* Não é necessário implementar autenticação
* Não é necessário seguir arquitetura avançada (DDD, CQRS, etc.)
* Uso de IA é permitido
* Foque em clareza, organização e funcionamento

---

Boa sorte! 🚀
