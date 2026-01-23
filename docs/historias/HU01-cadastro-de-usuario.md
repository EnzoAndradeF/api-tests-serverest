# HU01 - Cadastro de Usuário

### História de Usuário
**Como um visitante do sistema  
Quero me cadastrar como usuário  
Para que eu possa acessar e utilizar a aplicação**

### Regras de Negócio
1. O cadastro deve aceitar os seguintes campos:
   - nome
   - email
   - password
   - administrador (true ou false)

2. Todos os campos são obrigatórios
3. O campo **email deve ser único**
4. A senha deve conter no mínimo **5 caracteres**
5. Ao cadastrar com sucesso:
   - Status code: **201**
   - Deve retornar mensagem de sucesso
   - Deve retornar o **_id do usuário**
6. Não deve permitir cadastro com:
   - Email já existente
   - Campos vazios
   - Dados inválidos

## Casos de teste
### Caso de teste 01: 
---
| ID       | Descrição |
| :------- | :---------|
| C01-CT01 | Realizar o cadastro com credenciais válidas. |

| Campo       | Detalhe |
| :------- | :---------|
| **Pré-condições** | API Serverest disponível |
| **Método HTTP** | POST |
| **Endpoint** | /usuarios |
| **Headers** | Content-Type: application/json |

| Massa de dados |
|:---------------|
|"nome": "enzo comum",
  "email": "enzocomum@qa.com.br",
 "password": "teste",
  "administrador": "false" |

| **Ação** |
|:-------|
 Definir o método HTTP POST
 Definir o endpoint usuarios
 Preencher a propriedade “nome”
 Preencher a propriedade “email”
 Preencher a propriedade “password”
 Preencher a propriedade “administrador” |

| **Resultado Esperado** |
|:-------|
|O sistema deve retornar o status code 201, mensagem de sucesso e Id do usuário|

### Caso de teste 2: 
---
| ID       | Descrição |
| :------- | :---------|
| CT01-CT02 | Cadastro com campo "nome" vazio |

| Campo       | Detalhe |
| :------- | :---------|
| **Pré-condições** | API Serverest disponível |
| **Método HTTP** | POST |
| **Endpoint** | /usuarios |
| **Headers** | Content-Type: application/json |

| Massa de dados |
|:---------------|
|"nome": "",
  "email": "teste01.02@qa.com.br",
 "password": "teste",
  "administrador": "false" |

| **Ação** |
|:-------|
 Definir o método HTTP POST
 Definir o endpoint usuarios
 Preencher a propriedade “email”
 Preencher a propriedade “password”
 Preencher a propriedade “administrador” |

| **Resultado Esperado** |
|:-------|
|O sistema deve retornar o status code 400, e mensagem de erro|

### Caso de teste 3: 
----
| ID       | Descrição |
| :------- | :---------|
| CT01-CT03 | Cadastro com campo "email" vazio |

| Campo       | Detalhe |
| :------- | :---------|
| **Pré-condições** | API Serverest disponível |
| **Método HTTP** | POST |
| **Endpoint** | /usuarios |
| **Headers** | Content-Type: application/json |

| Massa de dados |
|:---------------|
|"nome": "teste01.03",
  "email": "",
 "password": "teste",
  "administrador": "false" |

| **Ação** |
|:-------|
 Definir o método HTTP POST
 Definir o endpoint usuarios
 Preencher a propriedade “nome”
 Preencher a propriedade “password”
 Preencher a propriedade “administrador” |

| **Resultado Esperado** |
|:-------|
|O sistema deve retornar o status code 400, e mensagem de erro|

### Caso de teste 4: 
----
| ID       | Descrição |
| :------- | :---------|
| CT01-CT04 | Cadastro com campo "password" vazio |

| Campo       | Detalhe |
| :------- | :---------|
| **Pré-condições** | API Serverest disponível |
| **Método HTTP** | POST |
| **Endpoint** | /usuarios |
| **Headers** | Content-Type: application/json |

| Massa de dados |
|:---------------|
|"nome": "teste01.03",
  "email": "teste01.03@qa.com.br",
 "password": "",
  "administrador": "false" |

| **Ação** |
|:-------|
 Definir o método HTTP POST
 Definir o endpoint usuarios
 Preencher a propriedade “nome”
 Preencher a propriedade “email”
 Preencher a propriedade “administrador” |

| **Resultado Esperado** |
|:-------|
|O sistema deve retornar o status code 400, e mensagem de erro|

### Caso de teste 5: 
----
| ID       | Descrição |
| :------- | :---------|
| CT01-CT05 | Cadastro com campo "administrador" vazio |

| Campo       | Detalhe |
| :------- | :---------|
| **Pré-condições** | API Serverest disponível |
| **Método HTTP** | POST |
| **Endpoint** | /usuarios |
| **Headers** | Content-Type: application/json |

| Massa de dados |
|:---------------|
|"nome": "teste01.04",
  "email": "teste01.04@qa.com.br",
 "password": "teste",
  "administrador": "" |

| **Ação** |
|:-------|
 Definir o método HTTP POST
 Definir o endpoint usuarios
 Preencher a propriedade “nome”
 Preencher a propriedade “email”
 Preencher a propriedade “password” |

| **Resultado Esperado** |
|:-------|
|O sistema deve retornar o status code 400, e mensagem de erro|

### Caso de teste 6: 
----
| ID       | Descrição |
| :------- | :---------|
| CT01-CT06 | Cadastro com campo email já cadastrado |

| Campo       | Detalhe |
| :------- | :---------|
| **Pré-condições** | API Serverest disponível / email cadastrado |
| **Método HTTP** | POST |
| **Endpoint** | /usuarios |
| **Headers** | Content-Type: application/json |

| Massa de dados |
|:---------------|
|"nome": "enzo",
  "email": "fulano@qa.com",
 "password": "teste",
  "administrador": "true" |

| **Ação** |
|:-------|
 Definir o método HTTP POST
 Definir o endpoint usuarios
 Preencher a propriedade “nome”
 Preencher a propriedade “email”
 Preencher a propriedade “password”
 Preencher a propriedade “administrador” |

| **Resultado Esperado** |
|:-------|
|O sistema deve retornar o status code 400, e mensagem de erro|

### Caso de teste 7: 
----
| ID       | Descrição |
| :------- | :---------|
| CT01-CT07 | Cadastro com senha de 4 caracteres |

| Campo       | Detalhe |
| :------- | :---------|
| **Pré-condições** | API Serverest disponível |
| **Método HTTP** | POST |
| **Endpoint** | /usuarios |
| **Headers** | Content-Type: application/json |

| Massa de dados |
|:---------------|
|"nome": "enzo",
  "email": "teste01.07@qa.com",
 "password": "test",
  "administrador": "true" |

| **Ação** |
|:-------|
 Definir o método HTTP POST
 Definir o endpoint usuarios
 Preencher a propriedade “nome”
 Preencher a propriedade “email”
 Preencher a propriedade “password”
 Preencher a propriedade “administrador” |

| **Resultado Esperado** |
|:-------|
|O sistema deve retornar o status code 400, e mensagem de erro|

### Caso de teste 8: 
----
| ID       | Descrição |
| :------- | :---------|
| CT01-CT08 | Cadastro com senha de 5 caracteres |

| Campo       | Detalhe |
| :------- | :---------|
| **Pré-condições** | API Serverest disponível |
| **Método HTTP** | POST |
| **Endpoint** | /usuarios |
| **Headers** | Content-Type: application/json |

| Massa de dados |
|:---------------|
|"nome": "enzo",
  "email": "teste01.08@qa.com",
 "password": "teste",
  "administrador": "true" |

| **Ação** |
|:-------|
 Definir o método HTTP POST
 Definir o endpoint usuarios
 Preencher a propriedade “nome”
 Preencher a propriedade “email”
 Preencher a propriedade “password”
 Preencher a propriedade “administrador” |

| **Resultado Esperado** |
|:-------|
|O sistema deve retornar o status code 201, e mensagem de sucesso|

### Caso de teste 9: 
----
| ID       | Descrição |
| :------- | :---------|
| CT01-CT09 | Cadastro com senha de 6 caracteres |

| Campo       | Detalhe |
| :------- | :---------|
| **Pré-condições** | API Serverest disponível |
| **Método HTTP** | POST |
| **Endpoint** | /usuarios |
| **Headers** | Content-Type: application/json |

| Massa de dados |
|:---------------|
|"nome": "enzo",
  "email": "teste01.09@qa.com",
 "password": "testes",
  "administrador": "true" |

| **Ação** |
|:-------|
 Definir o método HTTP POST
 Definir o endpoint usuarios
 Preencher a propriedade “nome”
 Preencher a propriedade “email”
 Preencher a propriedade “password”
 Preencher a propriedade “administrador” |

| **Resultado Esperado** |
|:-------|
|O sistema deve retornar o status code 201, e mensagem de sucesso|

## Evidências
Você pode encontrar a execução dos testes na pasta **[Cadastro de usuários](/evidencias/01%20-%20cadastro%20de%20usuario/)**.
