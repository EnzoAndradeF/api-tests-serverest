# HU02 - Login de Usuário

### História de Usuário
**Como usuário cadastrado  
Quero realizar login no sistema  
Para acessar funcionalidades restritas**

### Regras de Negócio
1. O login deve aceitar:
   - email
   - password

2. O email e senha devem corresponder a um usuário válido
3. Ao logar com sucesso:
   - Status code: **200**
   - Deve retornar um **token de autenticação**
4. O token deve ser utilizado nas requisições protegidas
5. Não deve permitir login com:
   - Email inexistente
   - Senha incorreta
   - Campos vazios

## Casos de teste
### Caso de teste 01: 
---
| ID       | Descrição |
| :------- | :---------|
| CT02.01 | Realizar o login com credenciais válidas. |

| Campo       | Detalhe |
| :------- | :---------|
| **Pré-condições** | API Serverest disponível / Usuário cadastrado |
| **Método HTTP** | POST |
| **Endpoint** | /login |
| **Headers** | Content-Type: application/json |

| Massa de dados |
|:---------------|
|"email": "fulano@qa.com",
  "password": "teste"
 |

| **Ação** |
|:-------|
 Definir o método HTTP POST
 Definir o endpoint
 Preencher a propriedade “email”
 Preencher a propriedade “password” |

| **Resultado Esperado** |
|:-------|
|O sistema deve retornar o status code 200, mensagem de sucesso e token de autorização|

### Caso de teste 02: 
---
| ID       | Descrição |
| :------- | :---------|
| CT02-CT02 | Realizar o login com email inexistente. |

| Campo       | Detalhe |
| :------- | :---------|
| **Pré-condições** | API Serverest disponível |
| **Método HTTP** | POST |
| **Endpoint** | /login |
| **Headers** | Content-Type: application/json |

| Massa de dados |
|:---------------|
|
  "email": "emailinexistente@qa.com.br",
 "password": "teste",
   |

| **Ação** |
|:-------|
 Definir o método HTTP POST
 Definir o endpoint
 Preencher a propriedade “email”
 Preencher a propriedade “password” |

| **Resultado Esperado** |
|:-------|
|O sistema deve retornar o status code 401 e mensagem de erro|

### Caso de teste 03: 
---
| ID       | Descrição |
| :------- | :---------|
| CT02.03 | Realizar o login com campos vazios. |

| Campo       | Detalhe |
| :------- | :---------|
| **Pré-condições** | API Serverest disponível |
| **Método HTTP** | POST |
| **Endpoint** | /login |
| **Headers** | Content-Type: application/json |

| Massa de dados |
|:---------------|
|"email": "",
 "password": "",
|

| **Ação** |
|:-------|
 Definir o método HTTP POST
 Definir o endpoint login
 |

| **Resultado Esperado** |
|:-------|
|O sistema deve retornar o status code 400 e mensagem de erro|

## Evidências
Você pode encontrar a execução dos testes na pasta **[Login](/evidencias/02%20-%20login/)**.