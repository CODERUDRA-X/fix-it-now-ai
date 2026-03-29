# 🏙️ Fix It Now
> AI-powered municipal complaint system — smart clustering, severity detection & map hotspot visualization

Built by **CODERUDRA-X**

---

## 📌 Problem
Municipal offices receive thousands of duplicate complaints daily.  
No smart way to know — *which complaint is most urgent? Which area needs attention first?*

## 💡 Solution
An AI system that:
- Detects **severity** of each complaint automatically
- **Clusters** similar complaints from the same area
- Assigns a **priority score** to each cluster
- Shows **live hotspots on a map** — so officers know exactly where to act first

---

## ✨ Features
| Feature | Description |
|--------|-------------|
| 📝 Complaint Submission | Text + location-based complaint form |
| 🧠 AI Severity Detection | LLM classifies: HIGH / MEDIUM / LOW |
| 🔗 Smart Clustering | Groups similar complaints using NLP embeddings |
| 📊 Priority Scoring | Score based on severity + cluster size + recency |
| 🗺️ Map Hotspot View | Red/Yellow/Green zones on interactive map |
| 🏛️ Officer Dashboard | Priority queue for city officers to take action |

---

## 🛠️ Tech Stack

### Frontend (Ujala)
- React.js
- Leaflet.js — interactive map
- Tailwind CSS
- Axios — API calls

### Backend (Shreyansh)
- FastAPI (Python)
- PostgreSQL + SQLAlchemy
- sentence-transformers — NLP embeddings
- Gemini API — severity detection
- scikit-learn — clustering (cosine similarity)

---

## 📁 Project Structure

```
civic-grievance-ai/
├── frontend/               # React app — Ujala
│   ├── src/
│   │   ├── components/
│   │   │   ├── ComplaintForm.jsx
│   │   │   ├── MapView.jsx
│   │   │   └── Dashboard.jsx
│   │   └── App.jsx
│   └── package.json
│
├── backend/                # FastAPI server — Shreyansh
│   ├── main.py
│   ├── models.py
│   ├── database.py
│   ├── ai/
│   │   ├── severity.py     # Gemini API severity detection
│   │   ├── embeddings.py   # sentence-transformers
│   │   └── clustering.py   # similarity + grouping
│   ├── routes/
│   │   ├── complaints.py
│   │   └── clusters.py
│   ├── requirements.txt
│   └── .env.example
│
└── README.md
```

---

## 🔄 How It Works

```
User submits complaint (text + location)
           ↓
   AI detects severity (HIGH/MED/LOW)
           ↓
  Embedding generated → similarity check
           ↓
  Grouped into cluster OR new cluster created
           ↓
  Priority score calculated (0–100)
           ↓
  Map updated with hotspot zone 🔴🟡🟢
```

---

## 🚀 Getting Started

### Backend Setup
```bash
cd backend
python -m venv venv
source venv/bin/activate  # Windows: venv\Scripts\activate
pip install -r requirements.txt
cp .env.example .env      # add your Gemini API key
uvicorn main:app --reload
```

### Frontend Setup
```bash
cd frontend
npm install
npm start
```

### Environment Variables (backend/.env)
```
DATABASE_URL=postgresql://user:password@localhost/grievance_db
GEMINI_API_KEY=your_key_here
```

---

## 📡 API Endpoints

| Method | Endpoint | Description |
|--------|----------|-------------|
| POST | `/complaint` | Submit a new complaint |
| GET | `/clusters` | Get all complaint clusters with scores |
| GET | `/hotspots` | GeoJSON data for map rendering |
| PUT | `/status/{id}` | Officer updates complaint status |
| GET | `/health` | Server health check |

---

## 🗓️ Build Timeline

| Day | Shreyansh | Ujala |
|-----|-----------|-------|
| Day 1 | FastAPI setup + DB schema | React setup + complaint form |
| Day 2 | Severity detection + embeddings | Map setup + hotspot markers |
| Day 3 | Clustering + priority score | Dashboard + API integration |
| Day 4 | All APIs complete + testing | UI polish + connect to backend |
| Day 5 | Deploy backend (Railway) | Deploy frontend (Vercel) |

---

## 🌐 Deployment
- **Frontend** → [Vercel](https://vercel.com)
- **Backend** → [Railway](https://railway.app)
- **Database** → Railway PostgreSQL (free tier)

---

## 👥 Team

| Name | Role | Branch |
|------|------|--------|
| Shreyansh Srivastava | Backend + AI Layer | CSE-DS, UIT Prayagraj |
| Ujala Saroj | Frontend + UI/UX | CSE-DS, UIT Prayagraj |

---

## 📄 License
MIT License — feel free to use and improve.
