# 🤖 AI Automation & n8n Agent Projects

![Timeline](https://img.shields.io/badge/Timeline-2026%20–%20Present-1E90FF?style=flat-square)
![Status](https://img.shields.io/badge/Status-Active%20Development-2ECC40?style=flat-square)
![Architecture](https://img.shields.io/badge/Architecture-AI%20Agents%20%2B%20Automation-F47C3C?style=flat-square)
![n8n](https://img.shields.io/badge/n8n-Workflow%20Automation-EA4B71?style=flat-square)
![Docker](https://img.shields.io/badge/Docker-Containerized-2496ED?style=flat-square\&logo=docker\&logoColor=white)
![Gemini](https://img.shields.io/badge/LLM-Google%20Gemini-4285F4?style=flat-square)
![WhatsApp](https://img.shields.io/badge/Integration-WhatsApp%20API-25D366?style=flat-square\&logo=whatsapp\&logoColor=white)
![Automation](https://img.shields.io/badge/Focus-Business%20Automation-8B5CF6?style=flat-square)

> A collection of real-world **AI automation workflows and agent systems** built using n8n.
> These projects focus on solving business problems through **AI Agents, workflow orchestration, and tool integration**.
> Designed for practical use cases like **sales automation, communication agents, and productivity systems**.

---

## 🗂️ Projects

| #  | Project                                                 | Description                                                                                                                                          | Stack                                              |
| -- | ------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------- | -------------------------------------------------- |
| 01 | [AI Proposal Generator](./01-AI-Proposal-Generator/) | AI-powered system that generates personalized sales proposals from a simple form input, ready for PDF export or client delivery                      | n8n · Gemini · Webhooks · JavaScript               |
| 02 | [WhatsApp AI Agent](./02-Whatsapp-AI-Agent/)               | Multi-modal AI assistant that handles text, voice, and images, and can perform actions like sending emails, scheduling events, and searching the web | n8n · Gemini · WhatsApp API · Tavily · Google APIs |

---

## 🏗️ Repository Structure

```
ai-automation-n8n/
│
├── README.md
│
├── ai-proposal-generator/
│   ├── README.md
│   └── workflow.json
│
├── whatsapp-ai-agent/
│   ├── README.md
│   └── workflow.json
│
└── docker-compose.yml
```

---

## 🧠 Skills Demonstrated

### 🤖 AI Agents & Automation

* Building agentic workflows using n8n
* Tool-based AI agents (email, calendar, search)
* Multi-step task execution from natural language
* Real-world business automation (sales, communication)

---

### 🔗 Workflow Orchestration

* Event-driven workflows using webhooks
* Conditional routing (text, audio, image)
* Multi-node pipeline design
* Error handling and fallback strategies

---

### 🧠 LLM Integration

* Prompt engineering for structured outputs (JSON)
* Using Gemini for generation, reasoning, and task execution
* Context-aware conversations with memory
* Transforming unstructured input into actionable data

---

### 📡 Multi-Modal Processing

* Speech-to-text (audio transcription)
* Image understanding and analysis
* Text normalization for unified AI processing

---

### 🔌 External Integrations

* WhatsApp API for real-time messaging
* Google Calendar (event creation)
* Gmail (automated email sending)
* Tavily (real-time web search)

---

### 🐳 Deployment & Infrastructure

* Docker-based self-hosting
* Workflow scalability considerations
* API-based system design
* Production-ready automation setup

---

## 📈 Project Progression

```
01 AI Proposal Generator   → structured AI outputs, business automation
        ↓
02 WhatsApp AI Agent      → multi-modal AI, tool usage, real-time interaction
```

Each project builds toward more advanced **agent autonomy, integration, and real-world usability**.

---

## 🛠️ Setup

Each project contains its own setup instructions.

### General Requirements

* n8n (self-hosted or cloud)
* Docker & Docker Compose
* API keys:

  * Google Gemini
  * WhatsApp API
  * Tavily
  * Google OAuth (Gmail & Calendar)

---

### Run with Docker

```bash
docker-compose up -d
```

---

### Import Workflows

* Open n8n UI
* Import workflow JSON files from each project folder
* Configure credentials

---

## 🛠️ Skills & Technologies

### ⚙️ Automation & Orchestration

![n8n](https://img.shields.io/badge/n8n-Workflow%20Automation-EA4B71?style=flat-square)
![Webhooks](https://img.shields.io/badge/Trigger-Webhooks-6366F1?style=flat-square)
![Automation](https://img.shields.io/badge/System-Automation%20Flows-6366F1?style=flat-square)

---

### 🤖 AI & LLMs

![Gemini](https://img.shields.io/badge/LLM-Google%20Gemini-4285F4?style=flat-square)
![Prompt Engineering](https://img.shields.io/badge/Skill-Prompt%20Engineering-8B5CF6?style=flat-square)
![AI Agents](https://img.shields.io/badge/System-AI%20Agents-DC2626?style=flat-square)

---

### 📡 Integrations & APIs

![WhatsApp](https://img.shields.io/badge/API-WhatsApp-25D366?style=flat-square)
![Gmail](https://img.shields.io/badge/API-Gmail-EA4335?style=flat-square)
![Google Calendar](https://img.shields.io/badge/API-Google%20Calendar-4285F4?style=flat-square)
![Tavily](https://img.shields.io/badge/API-Tavily%20Search-0F766E?style=flat-square)

---

### 🧠 Multi-Modal AI

![Speech to Text](https://img.shields.io/badge/AI-Speech%20to%20Text-10B981?style=flat-square)
![Image Analysis](https://img.shields.io/badge/AI-Image%20Understanding-F59E0B?style=flat-square)
![Text Processing](https://img.shields.io/badge/AI-Text%20Processing-3B82F6?style=flat-square)

---

### 🐳 Infrastructure

![Docker](https://img.shields.io/badge/Docker-Containerized-2496ED?style=flat-square\&logo=docker\&logoColor=white)
![Self Hosted](https://img.shields.io/badge/Deployment-Self--Hosted-4B5563?style=flat-square)

---

## ⚠️ Common Issues

### 🔴 Workflow Hanging

* Check Docker logs
* Ensure proper webhook response handling
* Add timeouts to API calls

### 🟡 No Response from Agent

* Verify WhatsApp API credentials
* Ensure final node returns output

### 🔵 Slow Execution

* Optimize AI prompts
* Reduce unnecessary tool calls

---

## 🚀 Future Work

* AI CRM Assistant
* Lead Qualification Agent
* Customer Support Automation Bot
* Advanced Memory & Context Systems

---

## 📬 Contact

**Sara Ibrahim**
📧 [saraomran433@gmail.com](mailto:saraomran433@gmail.com)

---
