
# 🚀 Desafio Técnico – API de Transações Simples

## 🧾 Objetivo

Construir uma API REST com Java e Spring Boot que permita o **registro de transações financeiras** e a **consulta de estatísticas básicas** sobre todas as transações salvas.

---

## 📌 Funcionalidades

### 1. Criar Transação

- **Endpoint**: `POST /transacoes`
- **Request Body (JSON)**:
```json
{
  "valor": 100.5,
  "dataHora": "2025-04-14T13:45:00Z"
}
```

- `valor`: número decimal positivo.
- `dataHora`: data e hora no padrão ISO 8601.

**Respostas esperadas:**

- `201 Created` – Transação salva com sucesso.
- `400 Bad Request` – Se o valor for negativo ou algum campo estiver ausente.

---

### 2. Consultar Estatísticas

- **Endpoint**: `GET /estatisticas`
- **Response Body (JSON)**:
```json
{
  "soma": 2350.75,
  "media": 1175.38,
  "min": 100.5,
  "max": 2250.25,
  "quantidade": 2
}
```

- Os dados retornam as estatísticas **de todas as transações registradas até agora**.

---

## 🎯 Requisitos Técnicos

- Projeto em Java com Spring Boot.
- API RESTful.
- Armazenamento em memória (ex: lista em Java) ou banco de dados relacional (opcional).
- Organização em camadas (Controller, Service, Repository).
- Boas práticas de codificação e tratamento de erros.

---

## 💡 Extras Opcionais (Desafio Plus)

- Persistência com banco de dados MySQL usando Spring Data JPA.
- Validações com `@Valid` e Bean Validation.
- Testes unitários com JUnit.
- Documentação com Swagger/OpenAPI.
- Deploy com Docker.

---

## ✅ Critérios de Avaliação

- Organização do projeto.
- Clareza e simplicidade do código.
- Funcionamento correto dos endpoints.
- Uso adequado das ferramentas do Spring.
- Validações e tratamento de erros.

---

Boa sorte e bons commits! 🚀
