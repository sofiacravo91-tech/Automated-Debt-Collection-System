# Automated-Debt-Collection-System

# Automated Debt Collection System

Sistema de automação de cobrança que prioriza clientes inadimplentes e realiza envios automáticos via **WhatsApp ou Email**, utilizando **n8n, Google Sheets e Puppeteer**.

O sistema foi desenvolvido para reduzir trabalho manual, organizar filas de cobrança e garantir envio inteligente baseado em prioridade e atraso.

---

# Arquitetura do Sistema

Google Sheets → Filtragem e priorização → Geração de mensagens → Envio automático

Workflow:

Google Sheets → Code (Filtrar e Priorizar)
             → Update (Agendado / Adiado)
             → Code (Gerar Links)
             → IF Canal
                → WhatsApp → Puppeteer Bot
                → Email → Gmail SMTP
             → Atualização de status na planilha

---

# Tecnologias utilizadas

- n8n (Workflow Automation)
- Google Sheets API
- Node.js
- Puppeteer
- Gmail SMTP
- WhatsApp Web Automation

---

# Estrutura da Carteira

Planilha Google Sheets com 239 clientes contendo:

| Campo | Descrição |
|------|------|
| Nome | Nome do cliente |
| Telefone | Telefone para WhatsApp |
| Email | Email do cliente |
| Canal | Canal de cobrança (WhatsApp / Email) |
| Dias de atraso | Tempo de inadimplência |
| Score | Score de cobrança |
| Prioridade | Peso na fila |
| Envio status | Agendado / Adiado / Enviado |
| Status | WhatsApp enviado / Email enviado |

---

# Lógica de Prioridade

O sistema filtra automaticamente:

- Clientes com **data ≤ hoje**
- **Status ativo**
- **Canal automático**
- **Envio status ≠ Enviado**

Após o filtro:

1. Ordena por  
   - Prioridade  
   - Score  
   - Dias de atraso  

2. Seleciona:
   - **20 primeiros → Agendado**
   - **Restante → Adiado**

---

# Envio via WhatsApp

Bot desenvolvido em **Node.js + Puppeteer**.

Funções:

- Abre sessão persistente
- Gera link de envio
- Abre conversa automaticamente
- Envia mensagem

Endpoint HTTP:

```
POST http://localhost:3001/enviar
```

Sessão armazenada em:

```
C:\cobranca-bot\whatsapp-session
```

---

# Envio via Email

Emails enviados via **Gmail SMTP** com template HTML.

Características:

- Layout profissional
- Sem marca n8n
- Personalização por cliente

---

# Automação diária

Workflow configurado para executar automaticamente às **08:00**.

Fluxo:

1. Ler carteira
2. Priorizar clientes
3. Enviar mensagens
4. Atualizar status
5. Registrar histórico

---

# Execução local

Iniciar n8n:

```bash
n8n start
```

Iniciar bot WhatsApp:

```bash
cd C:\cobranca-bot
node index.js
```

---

# Resultados

- Automação completa da cobrança
- Redução de trabalho manual
- Organização inteligente da carteira
- Envio multicanal automatizado

---

# Melhorias futuras

- Dashboard de cobrança
- Métricas de recuperação
- Integração com CRM
- IA para personalização de mensagens
