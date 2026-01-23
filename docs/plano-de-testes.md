# Plano de testes – API Petstore

## 1. Introdução
Este documento descreve a estratégia de testes adotada para validação da API **ServeRest**.

O objetivo é demonstrar capacidade de análise, definição de cenários de teste e validação do comportamento da API com base em requisitos funcionais.

---

## 2. Objetivo dos Testes
Garantir que os principais endpoints da API funcionem conforme esperado, validando:
- Fluxos principais de negócio
- Comportamento da API frente a entradas válidas e inválidas
- Estrutura das respostas (contrato)
- Códigos de status HTTP

---

## 3. Escopo dos Testes

### 3.1 Em Escopo
- Testes funcionais de API REST
- Testes de requisições HTTP (GET, POST, PUT, DELETE)
- Validação de códigos de status
- Validação de payload de resposta
- Testes negativos (dados inválidos ou incompletos)

### 3.2 Fora do Escopo
- Testes de performance
- Testes de carga e stress
- Testes de segurança
- Testes de compatibilidade
- Testes automatizados

---

## 4. Abordagem de Teste
Os testes serão realizados de forma **manual**, utilizando a ferramenta **Postman**, com base em histórias de usuário previamente definidas.

Cada história de usuário contém:
- Regras de negócio
- Casos de teste
- Referência às evidências de execução

---

## 5. Tipos de Teste Aplicados
- Testes funcionais
- Testes positivos
- Testes negativos

---

## 6. Técnicas de Teste Utilizadas
- Partição de Equivalência
- Análise de Valores Limite
- Testes baseados em regras de negócio

---

## 7. Critérios de Entrada
- API disponível e acessível
- Endpoints documentados via Swagger
- Ferramenta Postman configurada

---

## 8. Critérios de Saída
- Todos os casos de teste executados
- Evidências coletadas e documentadas
- Defeitos registrados quando identificados

---

## 9. Ambiente de Teste
- API pública Swagger Petstore
- Ferramenta de testes: Postman
- Execução local

---

## 10. Gerenciamento de Defeitos
Os defeitos encontrados são registrados em um relatório simples, contendo:
- Descrição do problema
- Endpoint afetado
- Comportamento esperado
- Comportamento obtido
- Evidência

---

## 11. Evidências de Teste
As evidências de execução dos testes estão armazenadas na pasta: **[Evidências](/evidencias/)**

