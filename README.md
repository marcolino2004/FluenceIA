# FluenceIA 🚀 | Democratizando o Acesso a Idiomas via WhatsApp

O **FluenceIA** é uma solução de automação educacional que utiliza o **n8n** como orquestrador central para transformar o WhatsApp em um tutor de idiomas personalizado. O projeto nasceu da necessidade de democratizar o acesso à informação e ao aprendizado de novas línguas, removendo barreiras linguísticas e financeiras para brasileiros que possuem rotinas intensas e pouco tempo para métodos tradicionais de estudo.

---

## 🕹️ Teste Agora

Para facilitar a avaliação da banca, você pode interagir diretamente com o fluxo configurado através do botão abaixo:

<div align="center">
    <a href="https://wa.me/5511965239692?text=Olá!%20Vim%20pelo%20repositório%20do%20n8n%20e%20gostaria%20de%20testar%20o%20FluenceIA." target="_blank">
        <img src="https://img.shields.io/badge/TESTAR%20NO%20WHATSAPP-25D366?style=for-the-badge&logo=whatsapp&logoColor=white" alt="Link para WhatsApp" height="60">
    </a>
</div>

---

## 🛠️ Stack Tecnológica

* **Orquestrador:** [n8n](https://n8n.io/)
* **Hospedagem:** Oracle Cloud
* **Engenharia de Software:** Windsurf & Devin
* **Interface:** WhatsApp Business API
* **Banco de Dados:** Supabase (PostgreSQL)
* **Inteligência Artificial:** OpenAI (Modelo: `gpt-5-mini`)
* **Framework de IA:** LangChain (Memória Dinâmica e Agentes)

---

## 🏗️ Arquitetura do Fluxo e Proposta Pedagógica

O workflow foi desenhado sob o princípio de **Máquina de Estados (State Machine)** e lógica de **Agentes Adaptativos**, focando em uma experiência de usuário (UX) fluida.

### 1. Triagem e Validação Inteligente de Dados
O sistema realiza um onboarding robusto para garantir a qualidade do cadastro e a personalização do ensino:
* **Validação via Regex:** O e-mail e os dados de contato passam por verificações de integridade para garantir uma comunicação precisa.
* **Extração de Entidades:** Utiliza JavaScript para limpar e tratar informações de **Nome**, **Idioma de Interesse** e **Nível Atual**, salvando-as de forma estruturada no Supabase.

### 2. IA Adaptativa por Níveis (Nivelamento Dinâmico)
A Inteligência Artificial não é genérica; ela se adapta ao nível de proficiência declarado pelo aluno:
* **Nível Básico:** Foco em alfabetização e vocabulário inicial, com alta incidência de **traduções para o português** para facilitar a compreensão.
* **Nível Intermediário:** Um modelo híbrido que mescla explicações gramaticais com prática de conversação.
* **Nível Avançado:** Foco total em **conversação direta**, simulando situações reais e imersão linguística total.

### 3. Memória Dinâmica e Vetores
Utilizamos princípios de **Memória Dinâmica** para que o bot recorde o progresso do aluno e o contexto das aulas anteriores. A integração com o Supabase permite que cada interação alimente o perfil do usuário, tornando o aprendizado cada vez mais assertivo.

---

## 🌍 Impacto Social e Democracia Digital

O brasileiro médio passa grande parte do dia no WhatsApp. Ao levar o ensino de idiomas para este aplicativo, o **FluenceIA** remove a barreira do "não tenho tempo" e do "não tenho acesso".
* **Democratização:** Educação de alta qualidade disponível 24h por dia para quem não pode pagar cursos caros.
* **Acessibilidade:** Interface simples que utiliza uma ferramenta que o brasileiro já domina.
* **Rotina:** O aprendizado acontece nos intervalos do dia a dia, de forma assíncrona e personalizada.

---

## 📊 Estrutura de Dados (Supabase)

O projeto depende de duas tabelas principais:
* `usuarios`: Dados cadastrais e preferências de idioma.
* `status_usuario`: Controle do estado do fluxo e progresso pedagógico.

---

## 🚀 Como Executar

1.  **Importação:** Importe o arquivo `fluxo_teste.json` para o seu n8n.
2.  **Credenciais:** Configure as conexões de WhatsApp API, Supabase e OpenAI.
3.  **Configuração:** Certifique-se de que as tabelas no Supabase seguem os campos referenciados no JSON para o correto funcionamento das chamadas SQL.

---

> **Desenvolvido por:** Anderson Marcolino e Lucas Oliveira
> *Engenheiro de Software focado em democratizar a tecnologia através da automação inteligente.*
,
> 
