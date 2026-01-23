## HU04 – Criação de Carrinho / Compra

### História de Usuário
**Como usuário autenticado  
Quero criar um carrinho de compras  
Para realizar uma compra de produtos**

### Regras de Negócio
1. O carrinho deve aceitar:
   - Lista de produtos
   - Quantidade de cada produto

2. O usuário deve estar autenticado
3. O produto deve existir
4. A quantidade solicitada não pode exceder o estoque disponível
5. Ao criar o carrinho com sucesso:
   - Status code: **201**
   - Deve retornar mensagem de sucesso
6. Não deve permitir:
   - Carrinho vazio
   - Produto inexistente
   - Quantidade maior que o estoque

## Casos de teste
### Caso de teste 01: 
---
| ID       | Descrição |
| :------- | :---------|
| CT04.01 | Realizar o criação de carrinho de compras. |

| Campo       | Detalhe |
| :------- | :---------|
| **Pré-condições** | API Serverest disponível / usuário autenticado |
| **Método HTTP** | POST |
| **Endpoint** | /carrinhos |
| **Headers** | Content-Type: application/json |

| Massa de dados |
|:---------------|  
|"iProduto":""
"quantidade":|

| **Ação** |
|:-------|
 Definir o método HTTP POST
 Definir o endpoint carrinhos
 Preencher a propriedade “idProduto”
 Preencher a propriedade “quantidade” |

| **Resultado Esperado** |
|:-------|
|O sistema deve retornar o status code 201, mensagem de sucesso e Id do carrinho|

### Caso de teste 02: 
---
| ID       | Descrição |
| :------- | :---------|
| CT04.02 | Adicionar quantidade de produto maior que estoque no carrinho. |

| Campo       | Detalhe |
| :------- | :---------|
| **Pré-condições** | API Serverest disponível / usuário autenticado |
| **Método HTTP** | POST |
| **Endpoint** | /carrinhos |
| **Headers** | Content-Type: application/json |

| Massa de dados |
|:---------------|  
|"idProduto": "PYmReWtX1ijiRY9u",
   "quantidade": 101|

| **Ação** |
|:-------|
 Definir o método HTTP POST
 Definir o endpoint carrinhos
 Preencher a propriedade “idProduto”
 Preencher a propriedade “quantidade” |

| **Resultado Esperado** |
|:-------|
|O sistema deve retornar o status code 400, mensagem de erro|

### Caso de teste 03: 
---
| ID       | Descrição |
| :------- | :---------|
| CT04.03 | Adicionar produto inexistente no carrinho. |

| Campo       | Detalhe |
| :------- | :---------|
| **Pré-condições** | API Serverest disponível / usuário autenticado |
| **Método HTTP** | POST |
| **Endpoint** | /carrinhos |
| **Headers** | Content-Type: application/json |

| Massa de dados |
|:---------------|  
|"iProduto": "inexistente",
"quantidade": 1|

| **Ação** |
|:-------|
 Definir o método HTTP POST
 Definir o endpoint carrinhos
 Preencher a propriedade “idProduto”
 Preencher a propriedade “quantidade” |

| **Resultado Esperado** |
|:-------|
|O sistema deve retornar o status code 400, mensagem de erro|

### Caso de teste 04: 
---
| ID       | Descrição |
| :------- | :---------|
| CT04.04 | Criar carrinho de compras com campos vazios. |

| Campo       | Detalhe |
| :------- | :---------|
| **Pré-condições** | API Serverest disponível / usuário autenticado |
| **Método HTTP** | POST |
| **Endpoint** | /carrinhos |
| **Headers** | Content-Type: application/json |

| Massa de dados |
|:---------------|  
|"iProduto": "",
"quantidade": |

| **Ação** |
|:-------|
 Definir o método HTTP POST
 Definir o endpoint carrinhos
 Preencher a propriedade “idProduto”
 Preencher a propriedade “quantidade” |

| **Resultado Esperado** |
|:-------|
|O sistema deve retornar o status code 400, mensagem de erro|

## Evidências
Você pode encontrar a execução dos testes na pasta **[Criação de carrinho](/evidencias/04%20-%20Criação%20de%20carrinho/)**.