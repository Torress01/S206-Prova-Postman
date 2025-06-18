# Prova - Teste de API com Postman e Newman

Este repositório contém a resolução do exercício proposto na prova de Teste de API, utilizando a ferramenta Postman para criação e execução dos testes, e Newman para automação e geração de relatórios HTML.

## 🚀 API Utilizada

Para a realização dos testes, foi utilizada a **Fake Store API** (`https://fakestoreapi.com/`). Esta API é uma excelente opção para fins de teste, pois simula um ambiente de e-commerce com recursos como produtos, usuários e carrinhos, sem a necessidade de autenticação complexa ou manipulação de dados reais sensíveis.

**Observação Importante sobre a Persistência de Dados:**
A Fake Store API é uma API de simulação (mock/fake) e **não possui um banco de dados persistente**. Isso significa que:
* Operações de escrita (`POST`, `PUT`, `PATCH`, `DELETE`) **não salvam as alterações de forma duradoura**. A API apenas simula a resposta esperada para essas operações.
* Consequentemente, requisições `GET` subsequentes para um recurso alterado **retornarão os dados originais e não refletirão as mudanças feitas anteriormente**.

Devido a essa característica, os testes de alteração e criação (`POST` e `PATCH`) focam primariamente na validação do **código de status HTTP retornado** e na **estrutura e conteúdo da resposta imediata** da API. Isso garante que a API está respondendo conforme o esperado para cada tipo de requisição, mesmo que as alterações não sejam persistidas.

## 🧪 Cenários de Teste Desenvolvidos

Foram desenvolvidos 3 cenários de teste distintos, cada um contendo casos de teste específicos para cobrir diferentes aspectos da API, incluindo cenários positivos e negativos.

### 1. Gerenciamento de Produtos (Criação e Leitura)

### 2. Gerenciamento de Usuários

### 3. Autenticação e Dados Inválidos (Cenário Negativo)
* **3.1 Autenticação com Credenciais Inválidas (POST - Negativo):** Verifica se a API rejeita tentativas de login com credenciais incorretas, retornando um status de erro (e.g., 401 Unauthorized).


## 🛠️ Como Executar os Testes

Para executar os testes contidos neste repositório, você precisará ter o Node.js e o Newman instalados em seu sistema.

### Pré-requisitos

1.  **Node.js e npm:** 
2.  **Newman:** 
    ```bash
    npm install -g newman
    ```
3.  **Newman HTML Extra Reporter:** Para a geração do relatório HTML detalhado:
    ```bash
    npm install -g newman-reporter-htmlextra
    ```

### Passos para Execução

1.  **Clone o Repositório:**

2.  **Execute a Coleção do Postman com Newman:**
    O arquivo da coleção do Postman (contendo todas as requisições e seus testes) está localizado na raiz deste repositório (`prova_api_testes.json`).

    No terminal, dentro da pasta do projeto, execute o seguinte comando:
    ```bash
    newman run Prova.postman_collection.json -r htmlextra
    ```

## 📊 Relatório de Testes

Após a execução do comando Newman, um relatório de testes em formato HTML será gerado na raiz do projeto

Para visualizar o relatório, basta abrir o arquivo em qualquer navegador da web. Ele fornecerá um resumo detalhado da execução, incluindo o status (pass/fail) de cada teste e as informações de cada requisição e resposta.

---
