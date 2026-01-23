# Relatório de Bug – API

| Campo | Descrição |
|------|-----------|
| **Sistema / API** | ServeRest  |
| **Endpoint** | /usuarios |
| **QA responsável** | Enzo Andrade |
| **Data** | 23/01/2026 |



## Bug 01: 

| Campo | Descrição |
|------|--------|
| **ID** | BUG-API-001 |
| **Título** | Cadastro com senha pequena |
| **Descrição** | Quando o usuário cadastra uma senha com a quantidade de caractere inferior a 5, então o cadastro é realizado com sucesso, quando deveria impedir o cadastro e aparecer uma mensagem informando que a senha é pequena |
| **Severidade** | Baixa |
| **Prioridade** | Alta  |
| **Status** | Aberto |

---

### Passos para Reproduzir

| # | **Ação** |
|---|------|
| 1 | Garantir que a API esteja disponível |
| 2 | Enviar requisição para o endpoint |
| 3 | Informar payload conforme descrito |
| 4 | Enviar a requisição |

---

### Requisição

| Campo | Detalhe |
|------|--------|
| **Método HTTP** | POST |
| **Endpoint** | /usuarios |
| **Headers** | `Content-Type: application/json` |
| **Body (request)** | { "nome": "enzo","email": "teste01.07@qa.com","password": "test","administrador": "true" }
 |

---

### Resposta

| Campo | Detalhe |
|------|--------|
| **Status HTTP obtido** | 201 |
| **Body (response)** | { "message": "Cadastro realizado com sucesso", "_id": "yoDSgLb6qfKOcwTy"} |

---

### Resultado

| Esperado | Obtido |
|----------|--------|
| Status code 400 e mensaagem de erro |  Status code 201 e cadastro realizado com sucesso |

---

### Ambiente

| Campo | Detalhe |
|------|--------|
| **Ambiente** | Homologação  |
| **Ferramenta** | Postman |
| **Sistema Operacional** | Windows |
| **Versão da API** | 2.29.7|

---

### Rastreabilidade

| Item | Referência |
|------|------------|
| **Caso de Teste** | CT01.07 |
| **Condição de Teste** | Cadastro de usuário |
| **Requisito** | A senha deve conter no mínimo 5 caracteres |


