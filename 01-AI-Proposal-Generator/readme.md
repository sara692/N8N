# 🤖 AI Proposal Generator

> Automatically generate professional sales proposals in under 10 seconds using N8N automation, Google Gemini AI, and a Lovable front-end dashboard.

---

## 📸 Workflow Screenshot

<img width="1743" height="550" alt="image" src="https://github.com/user-attachments/assets/9817ec78-90b4-4e88-88ea-ec15fa3f1b59" />

---

## 🖥️ App Screenshots

| Dashboard | 
|----------------------------|
| <img width="1895" height="891" alt="Capture 1" src="https://github.com/user-attachments/assets/31c8ddd3-92c7-4128-952d-7afa7a1114cf" /> |

| New Proposal Form |
|----------------------------|
| <img width="1874" height="908" alt="Capture 2" src="https://github.com/user-attachments/assets/ce0186d7-c0cd-4699-a816-b5d19e298e06" /> |

| Proposal Detail  |
|--------------------------------|
| <img width="1885" height="910" alt="Capture 3" src="https://github.com/user-attachments/assets/00f0c87e-65fd-4984-9516-4bb8b765c745" />
| <img width="1876" height="875" alt="Capture 4" src="https://github.com/user-attachments/assets/47c14325-cacf-41b8-afbe-30945808dfc9" />
| <img width="1886" height="896" alt="Capture 5" src="https://github.com/user-attachments/assets/9149ae78-ed04-4028-910d-014321c2676f" />
| <img width="1879" height="906" alt="Capture 6" src="https://github.com/user-attachments/assets/cb51c95d-8510-46bd-a490-a57df9f0f896" />

---

## ✨ What This Project Does

A marketing agency fills in a short form (prospect name, company, service needed, budget, pain points). The system automatically writes a full, personalised sales proposal using AI and returns it to the dashboard — ready to download as PDF or send to the client.

| Before | After |
|--------|-------|
| 60–90 minutes writing each proposal manually | Fill a 2-minute form → get a complete PDF proposal in **10 seconds** |

---

## 🔁 Workflow Overview

```
Webhook → Edit Fields → AI Agent (Gemini) → Code in JavaScript → Respond to Webhook
```

| Node | Type | Purpose |
|------|------|---------|
| Webhook | Trigger | Receives form data from Lovable via POST request |
| Edit Fields | Set Node | Stores the agency's service packages and pricing |
| AI Agent | Google Gemini Chat Model | Writes the full proposal as structured JSON |
| Code in JavaScript | Code Node | Parses and cleans Gemini output, structures final response |
| Respond to Webhook | Output | Sends the proposal JSON back to Lovable |

---

## 🧩 N8N Workflow — Node Details

### 1. Webhook Node

- **Method:** POST  
- **Path:** `/generate-proposal`  
- **Response Mode:** Using Respond to Webhook Node

**Receives:**
```json
{
  "contactName": "Sara",
  "companyName": "Stars",
  "email": "sara@stars.com",
  "companyWebsite": "https://stars.com",
  "service": "Social Media Management",
  "budget": "$800",
  "painPoints": "No content strategy, random posting",
  "extraContext": ""
}
```

---

### 2. Edit Fields Node (Set Node)

- **Mode:** JSON  
- **Stores:** Agency service catalogue

```json
{
  "services": [
    {
      "name": "Social Media Management",
      "price": "$800/mo",
      "deliverables": "12 posts/month, content calendar, community management, monthly report"
    },
    {
      "name": "Paid Ads / PPC",
      "price": "$600/mo + 10% ad spend",
      "deliverables": "Campaign setup, weekly optimization, conversion tracking, bi-weekly report"
    },
    {
      "name": "SEO & Content",
      "price": "$1,200/mo",
      "deliverables": "4 blog posts/month, keyword research, technical audit, ranking report"
    },
    {
      "name": "Email Marketing",
      "price": "$500/mo",
      "deliverables": "4 email campaigns/month, list segmentation, automation setup, open rate report"
    },
    {
      "name": "Brand Strategy",
      "price": "$1,500 one-time",
      "deliverables": "Brand positioning, tone of voice guide, competitor analysis, visual identity brief"
    }
  ]
}
```

---

### 3. AI Agent Node (Google Gemini Chat Model)

- **Model:** `gemini-2.5-flash`  
- **Credential:** Google AI Studio API Key (free tier)

**System Message:**
```
You are an expert sales copywriter for a digital marketing agency. 
When given prospect details, you write a professional, persuasive 
sales proposal. You respond ONLY with valid JSON — no extra text, 
no markdown, no backticks. Start directly with { and end with }.
```

**User Message:**
```
Write a sales proposal for this prospect:

- Company: {{ JSON.parse($('Webhook').item.json.body).companyName }}
- Contact: {{ JSON.parse($('Webhook').item.json.body).contactName }}
- Service wanted: {{ JSON.parse($('Webhook').item.json.body).service }}
- Budget: {{ JSON.parse($('Webhook').item.json.body).budget }}
- Pain points: {{ JSON.parse($('Webhook').item.json.body).painPoints }}
- Website: {{ JSON.parse($('Webhook').item.json.body).companyWebsite }}

Our available services:
{{ $('Edit Fields').item.json.services.map(s => s.name + ': ' + s.price + ' — ' + s.deliverables).join('\n') }}

Return ONLY this JSON structure:
{
  "executive_summary": "",
  "problem_statement": "",
  "proposed_solution": "",
  "scope_of_work": "",
  "pricing_table": [{"name": "", "description": "", "price": ""}],
  "timeline": [{"name": "", "duration": ""}],
  "why_us": "",
  "next_steps": ""
}
```

---

### 4. Code in JavaScript Node

```javascript
// Get the raw text from Gemini
const inputData = $input.first().json;

const rawText = 
  inputData.text ||
  inputData.content ||
  inputData.message?.content ||
  JSON.stringify(inputData);

// Clean off any backticks if Gemini added them
const clean = rawText.replace(/```json|```/g, '').trim();

// Parse proposal
const proposal = JSON.parse(clean);

// Get body — handle both string and object
const rawBody = $('Webhook').item.json.body;
const body = typeof rawBody === 'string' ? JSON.parse(rawBody) : rawBody;

return [{
  json: {
    status: "complete",
    company_name: body.companyName,
    contact_name: body.contactName,
    proposal: proposal
  }
}];
```

---

### 5. Respond to Webhook Node

- **Respond With:** First Incoming Item  
- Sends the full Code node output back to Lovable as the HTTP response

---

## 🎨 Front-end — Lovable App

Built with Lovable (React). The app has three main pages:

| Page | Purpose |
|------|---------|
| Dashboard | Lists all generated proposals with status badges |
| New Proposal | Form to enter prospect details and trigger the workflow |
| Proposal Detail | Displays the AI-generated proposal with all sections and PDF download |

**Webhook Integration:**
```javascript
const response = await fetch('YOUR_NGROK_OR_PUBLIC_URL/webhook/generate-proposal', {
  method: 'POST',
  body: JSON.stringify(formData)
});
const data = await response.json();
// data.proposal.output contains the JSON string — parse it
const proposal = JSON.parse(data.proposal.output);
```

---

## ⚙️ Setup Instructions

### Requirements

- N8N (self-hosted via Docker or cloud)
- Google AI Studio account (free) — [aistudio.google.com](https://aistudio.google.com)
- ngrok (for local testing) or a public N8N URL

---

### Step 1 — Get Gemini API Key

1. Go to [aistudio.google.com](https://aistudio.google.com)
2. Click **Get API Key → Create API Key**
3. Copy the key

### Step 2 — Import Workflow

1. Open N8N
2. Create a new workflow
3. Build nodes in this order: `Webhook → Edit Fields → AI Agent → Code in JavaScript → Respond to Webhook`
4. In the AI Agent node, add your Gemini API key as a credential

### Step 3 — Expose N8N (for local testing)

```bash
ngrok http 5678
```

Copy the `https://` URL and use it as your webhook base URL.

### Step 4 — Activate Workflow

- Toggle the workflow to **Active** in N8N
- Use `/webhook/generate-proposal` (not `/webhook-test/`) for production

### Step 5 — Connect Lovable

- Set the webhook URL in `NewProposal.tsx`
- Make sure to parse `data.proposal.output` when the response returns

---

## 📦 Proposal Output Structure

```json
{
  "status": "complete",
  "company_name": "Stars",
  "contact_name": "Sara",
  "proposal": {
    "output": "{\"executive_summary\": \"...\", \"problem_statement\": \"...\", ...}"
  }
}
```

> ⚠️ The `proposal.output` field is a JSON string — parse it on the front-end:
> ```javascript
> const sections = JSON.parse(data.proposal.output);
> ```

### Proposal Sections Displayed

| Section | Field |
|---------|-------|
| Executive Summary | `executive_summary` |
| The Challenge | `problem_statement` |
| Our Solution | `proposed_solution` |
| Scope of Work | `scope_of_work` |
| Investment | `pricing_table` (array) |
| Timeline | `timeline` (array) |
| Why Us | `why_us` |
| Next Steps | `next_steps` |

---

## 🐛 Known Issues & Fixes

| Issue | Cause | Fix |
|-------|-------|-----|
| `[undefined]` in prompt | Body arrives as string | Use `JSON.parse($('Webhook').item.json.body).fieldName` |
| `[object Object]` for services | Wrong serialization | Use `.map(s => s.name + ': ' + s.price).join('\n')` |
| Proposal sections not showing | Nested in `proposal.output` | Parse with `JSON.parse(data.proposal.output)` on front-end |
| Data lost on refresh | React state only | Use `localStorage` or Supabase to persist data |
| Unused Respond to Webhook error | Wrong Response Mode | Set Webhook node Response Mode to **Using Respond to Webhook Node** |

---

## 🛠️ Tech Stack

| Tool | Role |
|------|------|
| N8N (Docker) | Workflow automation engine |
| Google Gemini 2.5 Flash | AI proposal writing (free tier) |
| Lovable | React front-end dashboard |
| ngrok | Tunnel for local development |
| jsPDF | PDF generation in browser |

---

## 👤 Project By

**AI Agents Studio**  
Automating proposals for marketing agencies using N8N + AI  
📧 saraomran433@gmail.com
