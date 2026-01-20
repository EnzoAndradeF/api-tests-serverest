# HU01 - Cadastro Pet

## História de usuário

**Como usuário do sistema Petstore
Quero cadastrar um novo pet
Para que ele fique disponível para consulta e venda**

## Regras de negócio

1. O cadastro deve aceitar:
    - id
    - name
    - status (available, pending, sold)

2. O campo name é obrigatório
3. O campo status deve aceitar apenas valores válidos
4. Ao cadastrar com sucesso:
    - Status code: 200
    - O pet deve poder ser consultado pelo id

5. Não deve permitir cadastro com payload inválido

## Mind map



## Casos de teste
|**ID**|**Descrição**|**Pré-condições**|
|:-----|:------------|:------------|
| | | |


**Dados da requisição:**

| Campo | Descrição |
|------|----------|
| **Objetivo** | Validar o cadastro de um pet com dados válidos |
| **Pré-condições** | API Petstore disponível |
| **Método HTTP** | POST |
| **Endpoint** | /pet |
| **Headers** | Content-Type: application/json |
| **Massa de Dados** | `{ "id": 123, "name": "Rex", "status": "available" }` |
| **Ação** | Enviar requisição POST com payload válido |
| **Resultado Esperado** | Status 200 e retorno dos dados do pet cadastrado |


