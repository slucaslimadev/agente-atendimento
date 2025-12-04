# 🤖 Assistente Virtual Omnichannel com IA Generativa (Varejo)

> Automação de atendimento ao cliente para loja de celulares e acessórios, utilizando orquestração de Agentes de IA via n8n.

## 📌 Sobre o Projeto

Este projeto consiste em um fluxo de automação inteligente desenvolvido em **n8n** (Low-Code) que atua como um centralizador de atendimento para uma loja de varejo. O sistema é capaz de receber interações de múltiplos canais (WhatsApp e Instagram), interpretar a intenção do usuário (mesmo com áudio ou imagens) e direcionar para o agente especializado correto.

O objetivo principal é reduzir o tempo de resposta inicial e garantir que dados valiosos do atendimento sejam registrados automaticamente para análise futura.

## 🛠️ Tecnologias Utilizadas

* **Orquestração & Lógica:** [n8n](https://n8n.io/)
* **Inteligência Artificial:** OpenAI API (GPT-4o-mini)
* **Integração WhatsApp:** Evolution API
* **Banco de Dados / Logs:** Google Sheets
* **Canais:** WhatsApp e Instagram

## ⚙️ Arquitetura do Fluxo

O fluxo opera seguindo uma lógica de **Agentes Especializados**, garantindo que o contexto não se perca.

1.  **Entrada Multimodal (Triggers):**
    * **WhatsApp:** Recebimento via Webhook da Evolution API.
    * **Instagram:** Recebimento via Webhook direto.
    * *Capacidade:* O fluxo identifica e processa Texto, Áudio (transcrição) e Imagens.

2.  **Cérebro Central (Agente Triador):**
    * Um agente de IA analisa a entrada do usuário para classificar a intenção.
    * **Decisão:** Ele decide se a solicitação deve ser encaminhada para o fluxo de **Vendas** ou **Suporte/FAQ**.

3.  **Execução (Agentes Especializados):**
    * **Agente de Vendas:** Focado em conversão, apresentação de produtos e preços.
    * **Agente de Suporte:** Focado em tirar dúvidas de pós-venda, garantias e horários.

4.  **Logging e Analytics:**
    * Ao final de cada interação relevante, o sistema estrutura os dados (Cliente, Intenção, Resumo do Pedido/Dúvida) e salva em uma planilha do **Google Sheets** para controle gerencial.

## 🚀 Funcionalidades

- [x] **Atendimento Centralizado:** Um único fluxo gerencia múltiplos canais.
- [x] **Processamento de Áudio:** Capacidade de entender notas de voz enviadas pelos clientes.
- [x] **Roteamento Inteligente:** A IA decide qual o melhor caminho para o atendimento, evitando fluxos rígidos de "Digite 1 para...".
- [x] **Histórico Automatizado:** Registro de leads e atendimentos sem intervenção humana.

## 📂 Como Executar (Para Desenvolvedores)

Este projeto foi construído no **n8n**. Para replicar o funcionamento:

1.  Tenha uma instância do n8n rodando (Local, Docker ou Cloud).
2.  Importe o arquivo JSON do fluxo.
3.  Configure as Credenciais no n8n:
    * `OpenAI API Key`
    * `Google Sheets OAuth2`
    * `Evolution API Token`
4.  Ajuste os nós de Webhook com as URLs da sua instância.

---

### 👤 Autor

**Lucas dos Santos Lima**
* [LinkedIn] https://www.linkedin.com/in/lucas-dos-santos-4b836b27a/
* Estudante de Análise e Desenvolvimento de Sistemas | Estagiário em CoE de Automação

---
*Este projeto foi desenvolvido para fins de estudo e portfólio na área de RPA e Hiperautomação.*
