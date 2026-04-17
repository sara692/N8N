# 🤖 N8N

A collection of **production-ready AI automation workflows** built with n8n, focused on real-world business use cases like sales automation, WhatsApp agents, and AI-powered operations.

Each project is modular, scalable, and designed to be deployed using Docker.

---

## 📂 Projects Included

### 1. 🧾 AI Sales Proposal Generator

Automates the creation of personalized sales proposals for marketing agencies.

**What it does:**

* Takes client input via form
* Uses AI to generate a full proposal
* Returns structured output ready for PDF or email

**Impact:**

* ⏳ Reduces proposal writing time from 60–90 minutes
* ⚡ Generates complete proposals in ~10 seconds

**Workflow:**

```
Webhook → Set Fields → AI Agent → Code → Respond
```

📄 [View Full Documentation](./ai-proposal-generator/README.md)

---

### 2. 💬 WhatsApp AI Agent (Multi-Tool Assistant)

An intelligent WhatsApp assistant that can understand text, voice, and images, and perform real-world actions like sending emails, searching the web, and scheduling events.

---

## 🧠 What This Agent Can Do

* 💬 Answer user questions using AI
* 🎤 Transcribe voice messages to text
* 🖼️ Analyze images and extract meaning
* 📅 Create Google Calendar events
* 📧 Send emails via Gmail
* 🌐 Search the web (Tavily)
* 🧠 Maintain conversation memory

---

## 🔄 Workflow Overview

```
WhatsApp Trigger
   ↓
Switch (Text / Audio / Image)
   ↓
Processing Layer:
   - Text مباشرة
   - Audio → Transcription → Text
   - Image → Analysis → Text
   ↓
AI Agent (Gemini + Memory + Tools)
   ↓
WhatsApp Sender
```

---

## 🧩 Workflow Components

### 📥 Input Layer

* **WhatsApp Trigger**
* **Switch Node**

  * Routes messages based on type:

    * Text
    * Audio
    * Image

---

### 🎤 Audio Processing

* Download media
* Convert to URL
* Transcribe audio → text

---

### 🖼️ Image Processing

* Download image
* Generate accessible URL
* Analyze image using AI
* Convert result → text

---

### 🤖 AI Agent

* **Model:** Gemini 2.5 Flash
* **Memory:** Simple Memory (context-aware replies)

**Handles:**

* Natural conversations
* Task execution
* Tool selection

---

### 🧰 Integrated Tools

#### 📅 Google Calendar

* Create events directly from chat

#### 🌐 Tavily Search

* Real-time web search

#### 📧 Gmail

* Send emails on behalf of the user

---

### 📤 Output Layer

* Sends final response back via WhatsApp

---

## ⚙️ Tech Stack

* **n8n (Self-hosted)**
* **Docker**
* **Google Gemini API**
* **WhatsApp API**
* **Tavily Search API**
* **Google Services (Gmail, Calendar)**

---

## 🚀 Getting Started

### 1. Clone Repository

```bash
git clone https://github.com/your-username/ai-n8n-projects.git
cd ai-n8n-projects
```

### 2. Run with Docker

```bash
docker-compose up -d
```

---

### 3. Configure Credentials in n8n

* Gemini API
* WhatsApp API
* Google OAuth (Gmail & Calendar)
* Tavily API

---

### 4. Import Workflows

* Import each project from its folder into n8n

---

## 📁 Project Structure

```
ai-n8n-projects/
│
├── ai-proposal-generator/
│   ├── workflow.json
│   └── README.md
│
├── whatsapp-ai-agent/
│   ├── workflow.json
│   └── README.md
│
└── docker-compose.yml
```

---

## 💡 Future Projects (Planned)

* CRM AI Assistant
* Automated Lead Qualification System
* AI Customer Support Bot
* Data Analysis Agent

---

## 🤝 Contributing

Feel free to fork, improve, and submit PRs.

---

## 📄 License

MIT License

---

## ✨ Author

### Name : sara Ibarhim Mohamed Omran
### Contact : saraomarn433@gamil.com
