# ECAN Tutorial 
##  Overview

The **ECAN Tutorial** is an interactive learning platform designed to help users understand and experiment with **MeTTa**, **ECAN**, and symbolic AI concepts through a simple and intuitive interface.

It provides:

* A **Flask backend** that runs MeTTa code and keeps session history
* A **Next.js frontend** where users type code, run it, and see results instantly
* A clean structure that allows anyone to learn, modify, and extend the project

The goal of the ECAN Tutorial is to make **MeTTa programming** and **ECAN logic** easier to explore by giving users:

* Real-time code execution
* Step-by-step replay of previous code
* Safe reset features
* A clear environment for learning and experimentation



---

##  Live Deployment (Render)

### Backend (Flask API)

Runs automatically using:

```
gunicorn app:app
```

### Frontend (Next.js)

Runs from `npm run start` after being built with:

```
npm run build
```

Render uses the `render.yaml` file to deploy **both services**.

---


---


### 1. Clone the Repo

```bash
git clone https://github.com/eyuel693/ecan-tutorial.git
cd ecan-tutorial
```

---

# Backend Setup (Flask + MeTTa)

### 1. Create virtual environment

```bash
cd backend
python3 -m venv .venv
source .venv/bin/activate   # On Windows: .venv\Scripts\activate
```

### 2. Install dependencies

```bash
pip install -r requirements.txt
```

### 3. Start backend (development mode)

```bash
python app.py
```

Backend will run at:

```
http://localhost:5000
```

---

# Frontend Setup (Next.js)

### 1. Install dependencies

```bash
cd frontend
npm install
```

### 2. Run development server

```bash
npm run dev
```

Frontend will run at:

```
http://localhost:3000
```

---

#  Connecting Frontend to Backend

Your frontend expects an environment variable:

```
NEXT_PUBLIC_BACKEND_URL=http://localhost:5000
```

When deployed on Render, this becomes:

```
https://ecan-tutorial.onrender.com
```

---

###  Running Locally (Important)

If you want to run the project on your local machine, **you must change the backend API URL** used by the frontend.

Open the file:

```
frontend/components/code-editor.tsx
```

Then replace the production backend URL:

```
https://ecan-tutorial.onrender.com
```

with your local Flask API URL:

```
http://127.0.0.1:5000
```

This ensures the frontend correctly communicates with your local backend during development.

---

Here is a **clean and professional** version of your sentence, perfect for including in your README:

---

### Configure CORS for Local Development

When running the backend locally, make sure to update the CORS configuration in `backend/app.py`.

Remove this line:

```
origins="https://ecan-tutorial-1.onrender.com"
```

And Put only:

```
CORS(app)
```
---
