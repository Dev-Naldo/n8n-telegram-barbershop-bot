# 💈 Barbershop Appointment Bot | Inteligência Artificial com n8n

Um bot de atendimento automatizado para o Telegram, projetado para atuar como assistente virtual de uma barbearia. O projeto utiliza fluxos do **n8n** para orquestrar a comunicação entre o usuário, a inteligência artificial do **Google Gemini** e ferramentas externas.

> **Status do Projeto:** 🟡 Em desenvolvimento (Core de IA funcional, integrações de banco de dados em depuração).

---

## 🎥 Demonstração
![Demonstração do Bot](https://drive.google.com/file/d/1xP_gsnmMgV6loEGh1L37wdqM1BE31u7t/view?usp=sharing)

---

## 🚀 Arquitetura e Tecnologias

O sistema foi estruturado com foco em automação baseada em nós (node-based automation), utilizando as seguintes tecnologias:

*   **n8n:** Orquestração do fluxo de dados e integrações (Trigger, Memory, Tools e Agent).
*   **Telegram API:** Interface de interação direta com o usuário final.
*   **Google Gemini (2.5 Flash / Flash-Lite):** Motor cognitivo do Agente de IA para processamento de linguagem natural e extração de entidades (Nome, Serviço, Dia, Horário).
*   **LangChain (via n8n):** Gerenciamento de memória de contexto (Window Buffer Memory) para manter a coerência durante a conversa.
*   **Google Sheets API:** Planejado para atuar como banco de dados relacional dos agendamentos.

---

## 🧠 Destaque: Engenharia de Prompt e Agente Autônomo

O maior diferencial deste projeto é a configuração do Agente de IA. Em vez de criar um fluxo rígido de "se/então" (if/else), o sistema utiliza engenharia de prompt avançada para que o bot conduza o funil de vendas de forma humanizada.

**Instrução Base (System Message) implementada no nó do Agente:**
> *"Você é um assistente de barbearia focado em agendamento. Siga RIGOROSAMENTE estas etapas: 1. NOME, 2. SERVIÇO, 3. DIA, 4. HORÁRIO. [...] OBRIGATÓRIO: Use alta variação de resposta e resultado. Nunca repita a mesma frase exata duas vezes. Seja natural, humano e adapte suas respostas ao que o cliente digitar..."*

Isso garante que o bot não quebre caso o usuário mude de assunto ou digite as informações fora de ordem.

---

## 🛠️ Limitações Conhecidas e Próximos Passos (Roadmap)

Atualmente, o processamento de linguagem natural e a interação com o usuário via Telegram estão operando perfeitamente. O projeto encontra-se na seguinte fase de refatoração:

- [x] Integração Webhook com Telegram
- [x] Agente Inteligente com Google Gemini
- [x] Memória de Contexto Operacional
- [x] Extração de Parâmetros (Nome, Serviço, etc.)
- [ ] **Depuração da API do Google Sheets:** Os nós operacionais (`Salvar_Nome`, `Salvar_Servico`, `Consultar_Disponibilidade`) já estão estruturados no fluxo visual `.json`. Atualmente, a gravação e leitura final dos dados passam por debugging devido a mapeamento e restrições de permissões da API do Google.

---

## 📂 Como visualizar a estrutura deste projeto

Como este projeto foi desenvolvido visualmente no n8n, os arquivos neste repositório estão em formato `.json` (a exportação nativa da plataforma). 

Para visualizar a arquitetura completa das conexões e nós:
1. Instale o n8n localmente (`npm install n8n -g` e depois `n8n start`) ou utilize uma instância cloud.
2. Na interface visual do n8n, clique em *Import from file*.
3. Selecione os arquivos `w8GXiPHVvaYJtohz-Barbershop_Appointment_Chatbot.json` ou `Yhz8BLW8HQlClp47-Telegram_Barbershop_Bot.json`.

---

### 👨‍💻 Autor

**Reinaldo** 
*Estudante de Engenharia de Software*
- GitHub: [@Dev-Naldo](https://github.com/Dev-Naldo)
- [Linkedin](https://www.linkedin.com/in/reinaldo-celestino-6990132b4/)
