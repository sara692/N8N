# 🤖 AI Automation & n8n Agent Projects

![Timeline](https://img.shields.io/badge/Timeline-2026%20–%20Present-1E90FF?style=flat-square)
![Status](https://img.shields.io/badge/Status-Active%20Development-2ECC40?style=flat-square)
![Architecture](https://img.shields.io/badge/Architecture-AI%20Agents%20%2B%20Automation-F47C3C?style=flat-square)
![n8n](https://img.shields.io/badge/n8n-Workflow%20Automation-EA4B71?style=flat-square)
![Docker](https://img.shields.io/badge/Docker-Containerized-2496ED?style=flat-square\&logo=docker\&logoColor=white)
![Gemini](https://img.shields.io/badge/LLM-Google%20Gemini-4285F4?style=flat-square)
![WhatsApp](https://img.shields.io/badge/Integration-WhatsApp%20API-25D366?style=flat-square\&logo=whatsapp\&logoColor=white)
![Google Sheets](https://img.shields.io/badge/Integration-Google%20Sheets-34A853?style=flat-square)
![Automation](https://img.shields.io/badge/Focus-Business%20Automation-8B5CF6?style=flat-square)

> A collection of real-world **AI automation workflows and agent systems** built using n8n.
>
> These projects focus on solving business problems through **AI agents, workflow orchestration, LLM integration, and external tools**.
>
> The portfolio covers practical use cases including **sales automation, restaurant ordering, customer communication, productivity, and multi-modal AI assistants**.

---

## 🗂️ Projects

| #  | Project                                                                      | Description                                                                                                                                       | Stack                                                |
| -- | ---------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------- | ---------------------------------------------------- |
| 01 | [AI Proposal Generator](./01-AI-Proposal-Generator/)                         | AI-powered system that generates personalized sales proposals from a simple form and produces a client-ready PDF.                                 | n8n · Gemini · Webhooks · JavaScript                 |
| 02 | [WhatsApp AI Agent](./02-Whatsapp-AI-Agent/)                                 | Multi-modal AI assistant that handles text, voice, and images while performing actions such as sending emails, scheduling events, and web search. | n8n · Gemini · WhatsApp API · Tavily · Google APIs   |
| 03 | [LUMIÈRE — AI Restaurant Ordering System](./03-Lumiere-Restaurant-Ordering/) | AI-powered restaurant website with automated order processing, chatbot interaction, order tracking, and Google Sheets integration.                | n8n · AI Agent · Google Sheets · HTML · Tailwind CSS |

---

# 🍽️ Featured Project — LUMIÈRE

**LUMIÈRE** is an AI-powered restaurant ordering system that connects a modern restaurant website with an automated n8n backend.

Customers can:

* Browse the restaurant menu
* Add items to their cart
* Submit an order
* Chat with **Chef Lumi**, an AI restaurant assistant
* Track their order status using their phone number

Behind the scenes, n8n processes incoming webhook events, uses an AI agent to extract and normalize order information, and stores structured data in **Google Sheets**.

### 🔄 System Flow

```text
Customer
   │
   ▼
Restaurant Website
   │
   ├── Order
   ├── Chat
   ├── Order Tracking
   └── Visitor Tracking
          │
          ▼
     n8n Webhook
          │
          ▼
      AI Agent
          │
          ▼
    JS Normalizer
          │
          ▼
    Google Sheets
```

### Key Technical Features

* AI-powered order processing
* AI chatbot with natural-language interaction
* Structured JSON extraction
* JavaScript data normalization
* Multiple webhook event types
* Google Sheets database-like storage
* Real-time order tracking
* Retry logic with exponential backoff
* Cairo timezone handling
* Error handling and fallback logic
* Frontend-to-n8n API integration

---

## 🧠 Skills Demonstrated

### 🤖 AI Agents & Automation

* Building agentic workflows using n8n
* AI-powered business process automation
* Tool-based AI agents
* Natural-language task execution
* Structured information extraction
* Context-aware chatbot interactions
* Automated order processing

---

### 🔗 Workflow Orchestration

* Event-driven workflows using webhooks
* Conditional routing based on event types
* Multi-node pipeline design
* Data transformation and normalization
* Error handling and fallback strategies
* Retry mechanisms with exponential backoff
* API-based workflow architecture

---

### 🧠 LLM Integration

* Prompt engineering for structured JSON output
* LLM-based information extraction
* Context-aware AI conversations
* Converting unstructured user input into structured business data
* Handling inconsistent LLM output
* JSON parsing and normalization
* AI-powered chatbot workflows

---

### 📡 Multi-Modal Processing

The portfolio includes AI systems capable of processing:

* Text
* Voice/audio
* Images
* Natural-language requests

The **WhatsApp AI Agent** demonstrates multi-modal interaction, while **LUMIÈRE** focuses on conversational ordering and structured business data extraction.

---

### 🔌 External Integrations

* WhatsApp API
* Google Gmail
* Google Calendar
* Google Sheets
* Tavily Web Search
* Webhooks
* REST-style API integrations

---

### 🌐 Frontend & API Integration

LUMIÈRE also demonstrates frontend-to-backend integration:

* HTML
* Tailwind CSS
* JavaScript
* Webhooks
* JSON payloads
* Client-side retry logic
* Cart and order management
* Real-time order tracking

---

### 🐳 Deployment & Infrastructure

* Docker-based self-hosting
* Self-hosted n8n
* Webhook-based architecture
* API-driven system design
* Environment configuration
* Production-oriented automation patterns

---

## 📈 Project Progression

```text
01 AI Proposal Generator
        │
        ▼
Structured AI outputs
Business automation
Webhook integration
        │
        ▼
02 WhatsApp AI Agent
        │
        ▼
Multi-modal AI
Tool calling
External API integrations
Real-time interaction
        │
        ▼
03 LUMIÈRE Restaurant Ordering System
        │
        ▼
AI-powered business workflow
Conversational ordering
Structured data extraction
Order tracking
Frontend + backend integration
Google Sheets automation
```

Each project builds toward more advanced **AI autonomy, workflow orchestration, system integration, and real-world business usability**.

---

# 🛠️ Technologies

### ⚙️ Automation & Orchestration

![n8n](https://img.shields.io/badge/n8n-Workflow%20Automation-EA4B71?style=flat-square)
![Webhooks](https://img.shields.io/badge/Trigger-Webhooks-6366F1?style=flat-square)
![Automation](https://img.shields.io/badge/System-Automation%20Flows-6366F1?style=flat-square)
![JSON](https://img.shields.io/badge/Data-JSON-000000?style=flat-square)

---

### 🤖 AI & LLMs

![Gemini](https://img.shields.io/badge/LLM-Google%20Gemini-4285F4?style=flat-square)
![Prompt Engineering](https://img.shields.io/badge/Skill-Prompt%20Engineering-8B5CF6?style=flat-square)
![AI Agents](https://img.shields.io/badge/System-AI%20Agents-DC2626?style=flat-square)
![Structured Output](https://img.shields.io/badge/AI-Structured%20Output-7C3AED?style=flat-square)

---

### 🌐 Frontend & Web

![HTML](https://img.shields.io/badge/Frontend-HTML-E34F26?style=flat-square\&logo=html5\&logoColor=white)
![Tailwind](https://img.shields.io/badge/CSS-Tailwind%20CSS-06B6D4?style=flat-square\&logo=tailwindcss\&logoColor=white)
![JavaScript](https://img.shields.io/badge/Language-JavaScript-F7DF1E?style=flat-square\&logo=javascript\&logoColor=black)

---

### 📡 Integrations & APIs

![WhatsApp](https://img.shields.io/badge/API-WhatsApp-25D366?style=flat-square\&logo=whatsapp\&logoColor=white)
![Gmail](https://img.shields.io/badge/API-Gmail-EA4335?style=flat-square\&logo=gmail\&logoColor=white)
![Google Calendar](https://img.shields.io/badge/API-Google%20Calendar-4285F4?style=flat-square)
![Google Sheets](https://img.shields.io/badge/API-Google%20Sheets-34A853?style=flat-square\&logo=googlesheets\&logoColor=white)
![Tavily](https://img.shields.io/badge/API-Tavily%20Search-0F766E?style=flat-square)

---

### 🧠 AI Processing

![Speech to Text](https://img.shields.io/badge/AI-Speech%20to%20Text-10B981?style=flat-square)
![Image Analysis](https://img.shields.io/badge/AI-Image%20Understanding-F59E0B?style=flat-square)
![Text Processing](https://img.shields.io/badge/AI-Text%20Processing-3B82F6?style=flat-square)
![Information Extraction](https://img.shields.io/badge/AI-Information%20Extraction-9333EA?style=flat-square)

---

### 🐳 Infrastructure

![Docker](https://img.shields.io/badge/Docker-Containerized-2496ED?style=flat-square\&logo=docker\&logoColor=white)
![Self Hosted](https://img.shields.io/badge/Deployment-Self--Hosted-4B5563?style=flat-square)

---

# 🏗️ Repository Structure

```text
ai-automation-n8n/
│
├── README.md
│
├── 01-AI-Proposal-Generator/
│   ├── README.md
│   └── workflow.json
│
├── 02-Whatsapp-AI-Agent/
│   ├── README.md
│   └── workflow.json
│
├── 03-Lumiere-Restaurant-Ordering/
│   ├── README.md
│   ├── index.html
│   └── workflow.json
│
└── docker-compose.yml
```

---

# 🛠️ Setup

Each project contains its own detailed setup instructions.

### General Requirements

* n8n — self-hosted or cloud
* Docker & Docker Compose
* Google Gemini API
* WhatsApp API
* Tavily API
* Google OAuth for Gmail & Calendar
* Google Sheets
* Public webhook URL for external integrations

---

## 🐳 Run n8n with Docker

```bash
docker-compose up -d
```

Then open the n8n interface and import the workflow JSON files from the individual project folders.

---

## 📥 Import Workflows

1. Open the n8n interface.
2. Import the project's workflow JSON.
3. Configure the required credentials.
4. Update webhook URLs.
5. Activate the workflow.
6. Test the integration from the corresponding frontend or service.

---

# ⚠️ Common Issues

### 🔴 Workflow Hanging

* Check Docker logs.
* Check n8n execution logs.
* Verify webhook response configuration.
* Add appropriate API timeouts.

### 🟡 No Response from Agent

* Verify API credentials.
* Check the AI Agent configuration.
* Ensure the final node returns the expected output.
* Review the n8n execution history.

### 🔵 Slow Execution

* Optimize AI prompts.
* Reduce unnecessary LLM calls.
* Reduce unnecessary tool calls.
* Use structured outputs where possible.

### 🟠 Invalid JSON from AI

* Enforce JSON-only output in the system prompt.
* Validate the response before processing.
* Use a normalization/parsing Code node.
* Add fallback handling for malformed responses.

---

# 🚀 Future Work

Planned additions include:

* AI CRM Assistant
* Lead Qualification Agent
* Customer Support Automation Bot
* Advanced Memory & Context Systems
* RAG-powered business assistants
* Automated WhatsApp sales agents
* AI appointment booking systems
* Multi-agent business workflows
* Database-backed automation systems

---

# 📬 Contact

**Sara Ibrahim**

📧 **[saraomran433@gmail.com](mailto:saraomran433@gmail.com)**
