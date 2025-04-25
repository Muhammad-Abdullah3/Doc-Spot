# 📚 DocSpot – Document Sharing & Forum Platform

DocSpot is a full-stack web application built with **React**, **Firebase Authentication**, **FastAPI**, and **MySQL**, allowing users to upload documents, participate in discussions, and manage a simulated wallet for purchasing paid documents.

---

## 🔧 Tech Stack

-   🧠 **Frontend**: React.js + Tailwind CSS
-   🔐 **Auth**: Firebase Authentication (Email/Password)
-   ⚙️ **Backend**: FastAPI + SQLAlchemy
-   🛢️ **Database**: MySQL (via Railway)
-   ☁️ **Hosting**: Vercel (frontend) & Railway (backend)

---

## 📁 Project Structure

    your-project/
    ├── frontend/           # React app (UI + Firebase)
    │   ├── src/
    │   │   ├── components/      # Navbar etc
    │   │   ├── pages/           # Login, Dashboard, Upload, Forum, Wallet
    │   │   ├── firebase.js
    │   │   └── App.js
    │   ├── public/
    │   ├── .env (optional)
    │   └── package.json
    │
    ├── backend/            # FastAPI app (APIs + DB)
    │   ├── app/
    │   │   ├── db/
    │   │   │   └── database.py
    │   │   ├── models/
    │   │   ├── routes/
    │   │   ├── schemas/
    │   │   └── main.py
    │   ├── .env
    │   └── requirements.txt
    │
    └── README.md

---

## 🚀 How to Run Locally

### 🧩 1. Clone the Repo






```bash
git clone https://github.com/yourusername/your-project.git
cd your-project
```

## 2. Install Backend (FastAPI)
```bash
cd backend
python -m venv venv
source venv/bin/activate   # On Windows use: venv\Scripts\activate
pip install -r requirements.txt
```

## 3. Install Frontend (React)
```bash
cd ../frontend
npm install
```

## 🔐 Environment Variables

### Backend Configuration
Create `backend/.env` file with:
```env
DATABASE_URL=mysql+pymysql://<username>:<password>@<host>:<port>/<dbname>
SECRET_KEY=your-secret-key
ALGORITHM=HS256
ACCESS_TOKEN_EXPIRE_MINUTES=30
```

### Frontend Firebase Configuration
Update `frontend/src/firebase.js`:
```javascript
import { initializeApp } from "firebase/app";
import { getAuth } from "firebase/auth";

const firebaseConfig = {
  apiKey: "YOUR_API_KEY",
  authDomain: "YOUR_AUTH_DOMAIN",
  projectId: "YOUR_PROJECT_ID",
  storageBucket: "YOUR_STORAGE_BUCKET",
  messagingSenderId: "YOUR_SENDER_ID",
  appId: "YOUR_APP_ID"
};

const app = initializeApp(firebaseConfig);
export const auth = getAuth(app);
```

## 🚀 Running the Application

### Start Backend Server
```bash
cd backend
uvicorn app.main:app --reload
```

### Start Frontend Development Server
```bash
cd ../frontend
npm start
```

## 🌐 Access the Application
- **Frontend**: http://localhost:3000
- **Backend API Docs**: http://localhost:8000/docs

## ☁️ Deployment

### Frontend Deployment (Vercel)
```bash
cd frontend
npm run build
vercel
```

### Backend Deployment (Railway)
1. Connect your GitHub repository
2. Select the backend directory
3. Add environment variables
4. Deploy!

## ✨ Features
| Feature | Description |
|---------|-------------|
| 🔐 Authentication | Firebase login/signup |
| 📤 Document Management | Upload/view documents |
| 💬 Community Forum | Threads and discussions |
| 💰 Wallet System | View balance, deposit, pay |
| 📊 Analytics | Track views/downloads |
| 🛒 Payment System | Free/paid document access |

## 🛠️ Tech Stack
- **Frontend**: React.js, Firebase Auth
- **Backend**: FastAPI, Python
- **Database**: MySQL
- **Deployment**: Vercel (Frontend), Railway (Backend)
