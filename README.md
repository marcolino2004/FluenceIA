# FluenceIA
# LearningFácil 🚀 | Onboarding Inteligente via WhatsApp

O **LearningFácil** é uma solução de automação educacional que utiliza o **n8n** como orquestrador central para transformar o WhatsApp em um tutor de idiomas personalizado. O sistema gerencia desde a captura de dados (onboarding) até a interação dinâmica com o aluno via Inteligência Artificial.

---

## 🛠️ Stack Tecnológica

* **Orquestrador:** [n8n](https://n8n.io/)
* **Hospedagem** Máquina Virtual Oracle
* **Interface de Usuário:** WhatsApp Business API
* **Banco de Dados:** Supabase (PostgreSQL)
* **Inteligência Artificial:** OpenAI (Modelo: `gpt-5-mini`)
* **Framework de IA:** LangChain (com Buffer Window Memory)

---

## 🏗️ Arquitetura do Fluxo

O workflow foi desenhado seguindo princípios de **Máquina de Estados (State Machine)**, garantindo que o sistema saiba exatamente em qual etapa do cadastro o usuário se encontra.

### 1. Triagem e Identificação
O fluxo inicia com um **WhatsApp Trigger** que captura a mensagem. Através de um nó de código JavaScript, o sistema valida a origem da mensagem e consulta o **Supabase** para verificar se o usuário já possui um registro ativo.

### 2. Onboarding Automatizado com Tratamento de Dados
Caso o usuário seja novo, o sistema inicia uma sequência de coleta de dados utilizando lógica de programação para garantir a qualidade da informação:
* **Nome:** Extração via JavaScript que limpa saudações e capitaliza o nome automaticamente.
* **E-mail:** Validação robusta utilizando **Regex** para garantir que apenas e-mails sintaticamente corretos sejam salvos.
* **Idiomas e Nível:** O fluxo identifica mais de 15 idiomas e 3 níveis de proficiência (Básico, Intermediário e Avançado) através de palavras-chave e normalização de texto (remoção de acentos e caracteres especiais).

### 3. Cérebro de IA (Agentic Workflow)
Após o cadastro, o controle é passado para um **AI Agent** (LangChain):
* **Memória de Contexto:** Utiliza um `Simple Memory` com janela de 3 mensagens para manter a fluidez da conversa.
* **Personalização:** O agente identifica se o usuário prefere um método de aprendizado livre ou guiado por perguntas.

---

## 📊 Estrutura de Dados (Supabase)

O projeto depende de duas tabelas principais:
* `usuarios`: Armazena dados cadastrais (nome, e-mail, telefone, idioma, nível).
* `status_usuario`: Controla o estado atual do fluxo (flags de requisição de dados) para evitar redundância nas perguntas.

---

## 🚀 Como Executar

1.  **Importação:** Importe o arquivo `fluxo_teste.json` para o seu n8n.
2.  **Credenciais:** Configure as seguintes conexões:
    * WhatsApp API (Número de origem)
    * Supabase (URL e Service Role Key)
    * OpenAI (API Key)
3.  **Banco de Dados:** Crie as tabelas `usuarios` e `status_usuario` no seu projeto Supabase conforme os campos referenciados no JSON.
