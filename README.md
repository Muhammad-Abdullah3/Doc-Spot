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
git clone [https://github.com/yourusername/your-project.git](https://github.com/yourusername/your-project.git)
cd your-project
📦 2. Install Backend (FastAPI)cd backend
python -m venv venv
source venv/bin/activate   # or venv\Scripts\activate on Windows
pip install -r requirements.txt
🌐 3. Install Frontend (React)cd ../frontend
npm install
🔐 Environment Variables📄 backend/.envDATABASE_URL=mysql+pymysql://<username>:<password>@<host>:<port>/<dbname>
You’ll get these values from Railway’s MySQL plugin or your own MySQL host.🔑 Firebase Config (Frontend)Update the Firebase config in frontend/src/firebase.js:const firebaseConfig = {
  apiKey: "YOUR_API_KEY",
  authDomain: "YOUR_AUTH_DOMAIN",
  projectId: "YOUR_PROJECT_ID",
  storageBucket: "YOUR_STORAGE_BUCKET",
  messagingSenderId: "YOUR_SENDER_ID",
  appId: "YOUR_APP_ID"
};
🏁 Run the App▶️ Backendcd backend
uvicorn app.main:app --reload
▶️ Frontendcd frontend
npm start
Visit:Frontend: http://localhost:3000Backend: http://localhost:8000/docs📦 DeploymentFrontend: VercelBackend: Railway🧠 Features🔐 Login & Signup with Firebase📤 Upload & view documents (free or paid)💬 Community forum threads💰 Simulated wallet system (view, deposit, pay)📈 Track views & downloads per document✅ .env Template for BackendCreate backend/.env:DATABASE_URL=mysql+pymysql://user:password@host:3306/dbname
And in your backend/app/db/database.py, make sure it reads from the environment:import os
from sqlalchemy import create_engine
from sqlalchemy.orm import sessionmaker
from dotenv import load_dotenv

load_dotenv()

DATABASE_URL = os.getenv("DATABASE_URL")
engine = create_engine(DATABASE_URL)
SessionLocal = sessionmaker(autocommit=False, autoflush=False, bind=engine)
