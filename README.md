# Relatório de Testes de API — Caixa Cinza (Supabase Auth)

Este repositório contém a documentação e os artefatos dos testes de API utilizando a abordagem **Caixa Cinza** para a rota de autenticação de usuários do Supabase, desenvolvido para a disciplina de Linguagens de Programação da FACENS.

---

## 🛠️ Configuração do Ambiente (Supabase & Postman)

As credenciais do projeto e os endpoints foram mapeados e configurados dentro do **Postman Desktop** utilizando variáveis de ambiente para garantir a segurança dos dados.

### Variáveis de Ambiente Configuradas:
*   `base_url`: `https://iyehjzqilsajtftabkk.supabase.co/auth/v1`
*   `api_key`: *(Publishable Key obtida no painel do Supabase)*
*   `email`: `teste@facens.com`
*   `password`: `12345678`

---

## 🚀 Estrutura da Requisição HTTP

Os testes foram direcionados para o serviço de autenticação (GoTrue) do Supabase.

*   **Endpoint:** `POST {{base_url}}/token?grant_type=password`
*   **Headers:**
    *   `apikey`: `{{api_key}}`
    *   `Content-Type`: `application/json`
*   **Body (JSON):**
```json
    {
      "email": "{{email}}",
      "password": "{{password}}"
    }
    ```

---

## 📊 Matriz de Cenários de Testes Executados

Abaixo está a tabela resumida dos testes realizados no Postman:

| ID do Teste | Cenário | Entrada | Resultado Esperado | Resultado Obtido | Status |
| :--- | :--- | :--- | :--- | :--- | :--- |
| **TC-01** | Login Válido | Credenciais corretas | Status 200 OK + Access Token | Status 200 OK com geração de token | **Sucesso** |
| **TC-02** | Senha Incorreta | Senha alterada para inválida | Status 400 Bad Request / Erro de Auth | Retornou erro de credenciais inválidas | **Sucesso** |
| **TC-03** | Campos Vazios | E-mail e senha como `""` | Erro de validação da API | Retornou erro de campos obrigatórios | **Sucesso** |

---

## 📁 Evidências do Projeto

### Painel do Supabase e Usuário Criado
![Dashboard](./prints/01_supabase_dashboard.png)
![Chaves de API](./prints/02_supabase_keys.png)
![Usuário Cadastrado](./prints/03_supabase_usuario.png)

### Ambiente no Postman
![Variáveis de Ambiente](./prints/04_postman_ambiente.png)

### Resultados dos Testes Práticos
#### Cenário 1: Login Efetuado com Sucesso (200 OK)
![Teste Sucesso](./prints/05_teste_sucesso_200.png)

#### Cenário 2: Falha por Senha Incorreta (400 Bad Request)
![Teste Erro Senha](./prints/06_teste_erro_senha.png)

---
## 🏗️ Estrutura de Pastas do Repositório
*   `/prints/` — Contém todas as capturas de tela das configurações e execuções.
*   `/planilha/` — Contém o arquivo `planilha_testes.xlsx` com o detalhamento analítico.
