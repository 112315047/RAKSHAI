

## Project Info

**URL**: https://rescue-ai-webb-ufmc.vercel.app/

# RakshAI 🚨  
**AI-Powered Multilingual Emergency Triage for Disaster Zones**

RakshAI is a lightweight, multilingual AI system designed to assist people during disasters by providing **real-time emergency triage, safety guidance, and prioritization** when human responders are overwhelmed.

> ⚠️ **Disclaimer:** RakshAI provides AI-based assistance only.  
> For life-threatening emergencies, always contact official emergency services.

---

## 🌍 Problem Statement
During disasters, emergency helplines are often overloaded.  
People report emergencies in different languages, networks are unreliable, and responders struggle to quickly identify **who needs help first**.

This delay can cost lives.

---

## 🎯 Solution
RakshAI acts as a **digital first responder** that:
- Accepts emergency reports in multiple languages
- Uses AI to classify urgency and priority
- Provides immediate, safe action steps
- Helps responders focus on the most critical cases first

---

## ✨ Core Features

### 🧑‍🤝‍🧑 Citizen Emergency Chat
- Multilingual chat (English, Hindi, Telugu, Tamil, Marathi)
- Emergency quick buttons (Fire, Flood, Accident, Trapped, Food/Water)
- WhatsApp-style chat interface
- Location input (text-based)
- AI-generated response cards:
  - Priority (P1–P4)
  - Urgency score (0–100)
  - Category
  - Immediate safety actions
  - Follow-up questions

---

### 🧠 AI Triage Engine
Each user message is analyzed to produce:
- **Priority Levels**
  - P1 🔴 Critical
  - P2 🟠 Urgent
  - P3 🟡 Moderate
  - P4 🟢 Low
- **Category** (medical, fire, flood, shelter, food, water, mental)
- **Urgency score**
- **Escalation flag** for human responders
- **Safe, non-harmful guidance only**

---

### 🎤 Voice Input (Low-Network Friendly)
- Short voice recording (≤ 6 seconds)
- Compressed audio upload
- Automatic speech-to-text
- Graceful fallback to text input if network fails

---

### 🧑‍🚒 Responder Dashboard
- Real-time case list sorted by urgency
- Priority color indicators
- View full conversation history
- Assign volunteers/responders
- Mark cases as resolved

---

## 🏗️ Tech Stack

| Layer | Technology |
|-----|-----------|
| Frontend | React (Vite) + TypeScript |
| UI Framework | TailwindCSS + Shadcn UI |
| Backend | Django REST Framework (Python) |
| Database | Supabase (PostgreSQL) |
| Realtime | Supabase Realtime |
| AI (Chat) | Lovable AI (Google Gemini / GPT-4) |
| AI (Voice) | OpenAI Whisper (via Edge Function) |
| Maps | Leaflet |
| Hosting | Vercel (Frontend) + *Self-Hosted/Cloud Run* (Backend) |

---

## 🚀 Getting Started

### Prerequisites
- Node.js (v18 or higher)
- Python 3.10+
- npm or yarn

### Installation

1. **Clone the repository**
   ```bash
   git clone https://github.com/yourusername/aidlink-ai.git
   cd aidlink-ai
   ```

2. **Frontend Setup**
   ```bash
   npm install
   ```

3. **Backend Setup**
   Open a new terminal:
   ```bash
   cd backend
   python -m venv venv
   # Windows:
   venv\Scripts\activate
   # Mac/Linux:
   # source venv/bin/activate
   pip install -r requirements.txt
   ```

4. **Environment Variables**
   - **Frontend**: Create `.env` in root with `VITE_SUPABASE_URL`, `VITE_SUPABASE_ANON_KEY`.
   - **Backend**: Create `.env` in `backend/` with `SUPABASE_URL`, `SUPABASE_KEY`.

5. **Run the Application**

   **Terminal 1 (Backend):**
   ```bash
   cd backend
   python manage.py runserver
   ```

   **Terminal 2 (Frontend):**
   ```bash
   npm run dev
   ```

---

## 🗄️ Database Structure (Supabase – PostgreSQL)

### 📌 Table: `cases`

| Column | Type | Description |
|------|------|-------------|
| id | uuid (PK) | Unique case ID |
| created_at | timestamp | Case creation time |
| status | text | active / resolved / assigned |
| language | text | User language |
| location | text | User-provided location |
| category | text | medical / fire / flood / shelter / food / water |
| urgency_score | integer | 0–100 urgency level |
| assigned_to | text | Assigned responder |

---

### 📌 Table: `messages`

| Column | Type | Description |
|------|------|-------------|
| id | uuid (PK) | Message ID |
| case_id | uuid (FK) | Related case |
| sender | text | user / ai |
| text | text | Message content |
| created_at | timestamp | Message time |

---

## 🛡️ Safety & Ethics
- No diagnosis or harmful medical advice
- Only general first-aid and safety guidance
- Human responders remain in control
- Clear AI disclaimer shown to users

---

## 🌱 SDG Alignment
- **SDG 3:** Good Health & Well-Being  
- **SDG 11:** Sustainable Cities & Communities  
- **SDG 9:** Resilient Infrastructure  

---

## 💰 Sustainability & Revenue Model
- Government and NGO disaster-response deployments
- White-label solution for municipalities
- CSR-funded emergency preparedness programs
- API access for humanitarian organizations

---

## 🧪 Demo Flow
1. User reports an emergency in their language
2. AI performs triage and gives safety steps
3. Case appears instantly on responder dashboard
4. Responder assigns help and resolves case

---

## 📌 Future Enhancements
- Offline-first PWA support
- SMS-based emergency reporting
- Automatic authority escalation
- Disaster heatmap and analytics

---

**RakshAI — Protecting lives when every second counts.**
