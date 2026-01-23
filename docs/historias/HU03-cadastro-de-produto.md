### HU03 – Cadastro de Produto (Usuário Administrador)

### História de Usuário
**Como usuário administrador  
Quero cadastrar um produto  
Para que ele possa ser vendido no sistema**

### Regras de Negócio
1. O cadastro deve aceitar:
   - nome
   - preco
   - descricao
   - quantidade

2. Apenas usuários com perfil **administrador** podem cadastrar produtos
3. A requisição deve conter:
   - Header `Authorization` com token válido
4. Ao cadastrar com sucesso:
   - Status code: **201**
   - Deve retornar o **_id do produto**
5. Não deve permitir cadastro com:
   - Token inválido ou ausente
   - Campos obrigatórios vazios
   - Valores inválidos (ex: preço negativo)

## Casos de teste
### Caso de teste 01: 
---
| ID       | Descrição |
| :------- | :---------|
| CT03.01 | Realizar o cadastro de produto com usuário administrador. |

| Campo       | Detalhe |
| :------- | :---------|
| **Pré-condições** | API Serverest disponível / usuário administrador autenticado |
| **Método HTTP** | POST |
| **Endpoint** | /produtos |
| **Headers** | Content-Type: application/json |

| Massa de dados |
|:---------------|
|  "nome": "notebook lenovo ideapad3",
  "preco": 700,
  "descricao": "Notebook"
   "quantidade": 100 |

| **Ação** |
|:-------|
 Definir o método HTTP POST
 Definir o endpoint produtos
 Preencher a propriedade “nome”
 Preencher a propriedade “preco”
 Preencher a propriedade “descricao”
 Preencher a propriedade “quantidade” |

| **Resultado Esperado** |
|:-------|
|O sistema deve retornar o status code 201, mensagem de sucesso e Id do produto|


### Caso de teste 02: 
---
| ID       | Descrição |
| :------- | :---------|
| CT03-CT02 | Realizar o cadastro de produto com nome existente. |

| Campo       | Detalhe |
| :------- | :---------|
| **Pré-condições** | API Serverest disponível / usuário administrador autenticado |
| **Método HTTP** | POST |
| **Endpoint** | /produtos |
| **Headers** | Content-Type: application/json |

| Massa de dados |
|:---------------|
|  "nome": "notebook lenovo ideapad3",
  "preco": 700,
  "descricao": "Notebook"
   "quantidade": 100 |

| **Ação** |
|:-------|
 Definir o método HTTP POST
 Definir o endpoint produtos
 Preencher a propriedade “nome”
 Preencher a propriedade “preco”
 Preencher a propriedade “descricao”
 Preencher a propriedade “quantidade” |

| **Resultado Esperado** |
|:-------|
|O sistema deve retornar o status code 400, mensagem de erro|

### Caso de teste 03: 
---
| ID       | Descrição |
| :------- | :---------|
| CT03.03 | Realizar o cadastro de produto com preço negativo. |

| Campo       | Detalhe |
| :------- | :---------|
| **Pré-condições** | API Serverest disponível / usuário administrador autenticado |
| **Método HTTP** | POST |
| **Endpoint** | /produtos |
| **Headers** | Content-Type: application/json |

| Massa de dados |
|:---------------|
|  "nome": "notebook lenovo ideapad4",
  "preco": -10,
  "descricao": "Notebook"
   "quantidade": 100 |

| **Ação** |
|:-------|
 Definir o método HTTP POST
 Definir o endpoint produtos
 Preencher a propriedade “nome”
 Preencher a propriedade “preco”
 Preencher a propriedade “descricao”
 Preencher a propriedade “quantidade” |

| **Resultado Esperado** |
|:-------|
|O sistema deve retornar o status code 400, mensagem de erro|

### Caso de teste 04: 
---
| ID       | Descrição |
| :------- | :---------|
| CT03.04 | Realizar o cadastro de produto com quantidade negativa. |

| Campo       | Detalhe |
| :------- | :---------|
| **Pré-condições** | API Serverest disponível / usuário administrador autenticado |
| **Método HTTP** | POST |
| **Endpoint** | /produtos |
| **Headers** | Content-Type: application/json |

| Massa de dados |
|:---------------|
|  "nome": "notebook lenovo ideapad5",
  "preco": 700,
  "descricao": "Notebook"
   "quantidade": -100 |

| **Ação** |
|:-------|
 Definir o método HTTP POST
 Definir o endpoint produtos
 Preencher a propriedade “nome”
 Preencher a propriedade “preco”
 Preencher a propriedade “descricao”
 Preencher a propriedade “quantidade” |

| **Resultado Esperado** |
|:-------|
|O sistema deve retornar o status code 400, mensagem de erro|

## Evidências
Você pode encontrar a execução dos testes na pasta **[Cadastro de produtos](/evidencias/03%20-%20Cadastro%20de%20produto/)**.