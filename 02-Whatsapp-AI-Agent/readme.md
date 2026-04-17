# 💬 WhatsApp AI Agent (Multi-Modal Assistant)

> An intelligent WhatsApp assistant powered by N8N and Google Gemini that understands text, voice, and images — and can perform real-world actions like sending emails, scheduling events, and searching the web.

---

## 📸 Workflow Screenshot
| <img width="1693" height="667" alt="Workflow" src="https://github.com/user-attachments/assets/67ee6e1a-36c3-44af-97e2-c99967290610" /> |

---

## 🖥️ Agent Capabilities

| Feature | Description |
|--------|------------|
| 💬 Chat | Answer user questions using AI |
| 🎤 Voice | Transcribe audio messages to text |
| 🖼️ Image | Analyze images and describe content |
| 📅 Calendar | Create events via Google Calendar |
| 📧 Email | Send emails using Gmail |
| 🌐 Web Search | Fetch real-time info using Tavily |
| 🧠 Memory | Maintain conversation context |

---

## ✨ What This Project Does

This project turns WhatsApp into a **fully functional AI assistant**.

Users can send:
- Text messages
- Voice notes
- Images

The system processes the input, converts everything into text, and uses an AI agent to:
- Understand intent
- Decide what action to take
- Execute tools (email, calendar, search)
- Respond back on WhatsApp

---

## 🔁 Workflow Overview

WhatsApp Trigger → Switch → Processing Layer → AI Agent (Gemini) → WhatsApp Sender
| <img width="1506" height="977" alt="Capture1" src="https://github.com/user-attachments/assets/f03abfe1-6fd4-4619-b617-218390593fc3" />
  <img width="1508" height="982" alt="Capture2" src="https://github.com/user-attachments/assets/e93d2805-27c8-4be3-802c-c2dd7e42ffaf" /> |


---

## 🧩 N8N Workflow — Node Details

### 1. WhatsApp Trigger

- **Type:** Trigger  
- **Purpose:** Receives incoming WhatsApp messages  

**Outputs:**
- text
- audio
- image

---

### 2. Switch Node

- **Mode:** Rules  
- **Purpose:** Routes input based on type  

| Route | Description |
|------|-------------|
| Text | Directly processed |
| Audio | Sent to transcription |
| Image | Sent to analysis |

---

## 🎤 Audio Processing

### Download Media
- Retrieves WhatsApp audio file

### Audio URL
- Converts file into accessible URL

### Transcribe Audio
- Converts speech → text using AI

### Audio to Text
- Final formatted text passed to agent

---

## 🖼️ Image Processing

### Download Media
- Retrieves image from WhatsApp

### Image URL
- Prepares image for AI processing

### Analyze Image
- Uses AI to understand image content

### Image to Text
- Converts output into text prompt

---

## 🤖 AI Agent (Google Gemini)

- **Model:** `gemini-2.5-flash`  
- **Memory:** Simple Memory  

**Responsibilities:**
- Understand user intent
- Generate responses
- Decide when to call tools

---

### System Behavior

**The agent acts as:**
- A smart assistant that can answer questions,
- send emails, create calendar events, and search the web.
- Always choose the appropriate tool when needed.


---

## 🧰 Tools Integration

### 📅 Google Calendar
- Create events directly from chat  
- Example:
  > “Schedule a meeting tomorrow at 3 PM”

---

### 📧 Gmail
- Send emails via WhatsApp  
- Example:
  > “Send an email to Sara confirming the AI event”

---

### 🌐 Tavily Search
- Real-time web search  
- Example:
  > “Latest news about AI”

---

## 📤 WhatsApp Sender

- Sends final AI response back to the user  
- Works for:
  - Text replies
  - Tool execution confirmations

---

## ⚙️ Setup Instructions

### Requirements

- N8N (self-hosted via Docker)
- WhatsApp API access
- Google AI Studio API key
- Tavily API key
- Google OAuth (Gmail & Calendar)

---

### Step 1 — Get API Keys

- Gemini → https://aistudio.google.com  
- Tavily → https://tavily.com  
- Google OAuth → Gmail + Calendar  

---

### Step 2 — Import Workflow

1. Open N8N  
2. Import workflow JSON  
3. Connect all credentials  

---

### Step 3 — Configure WhatsApp Trigger

- Connect your WhatsApp provider (e.g., Meta API or Twilio)
- Set webhook URL

---

### Step 4 — Activate Workflow

- Toggle workflow to **Active**
- Send message to your WhatsApp number

---

## 🧪 Example Commands

Try sending these messages:

### General
- “What’s the latest news about AI?”
- “Explain machine learning simply”

---

### Email
- “Send an email to saraomran433@gmail.com confirming tomorrow’s AI event”

---

### Calendar
- “Schedule a meeting tomorrow from 1 PM to 4 PM”

---

### Search
- “Search for the latest trends in generative AI”

---

### Multi-step Task
- “Find an AI event and add it to my calendar”

---

## 🐛 Known Issues & Fixes

| Issue | Cause | Fix |
|------|------|-----|
| No reply on WhatsApp | Missing response node | Ensure WhatsApp Sender is connected |
| Workflow hangs | Long API call | Add timeouts |
| Audio not transcribed | Invalid media URL | Verify download node |
| Tools not triggered | Weak prompt | Improve system instructions |

---

## 🛠️ Tech Stack

| Tool | Role |
|------|------|
| N8N (Docker) | Workflow automation |
| Google Gemini 2.5 Flash | AI reasoning & generation |
| WhatsApp API | Messaging interface |
| Tavily | Web search |
| Google APIs | Gmail & Calendar |

---

## 🚀 Future Improvements

- Memory persistence (database)
- Multi-user session handling
- Voice reply support
- Advanced agent planning
- RAG integration

---

## 👤 Project By

**AI Agents Studio**  
Building real-world AI automation systems with n8n  

📧 saraomran433@gmail.com
