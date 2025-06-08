
# 🧪 Institutional Aflatoxin Classification System

This repository provides a full-stack system designed to assess and classify aflatoxin contamination in institutional grain samples. It combines:

- **FastAPI** – Backend for serving the ML model and handling API requests
- **Next.js** – Frontend for institutional interfaces (Schools, Hospitals, Prisons, Mobile)
- **Jupyter Notebook** – Used for exploratory data analysis, feature engineering, and model training

---

## 📁 Project Structure

```
.
├── backend/            # FastAPI application (API Gateway, Auth, Notifications)
│   └── main.py
├── frontend/           # Next.js frontend (Dashboards and Interfaces)
│   └── pages/
│       └── index.tsx
├── notebook/           # Jupyter Notebook for ML model
│   └── aflatoxin_model.ipynb
├── models/             # Saved ML model files and preprocessing assets
├── requirements.txt    # Python dependencies
├── README.md
```

---

## 🚀 Getting Started

### 1. Clone the Repository

```bash
git clone https://github.com/your-username/aflatoxin-classification.git
cd aflatoxin-classification
```

---

### 2. Backend (FastAPI)

```bash
cd backend
python -m venv venv
source venv/bin/activate  # On Windows: venv\Scripts\activate
pip install -r ../requirements.txt
uvicorn main:app --reload
```

---

### 3. Frontend (Next.js)

```bash
cd ../frontend
npm install
npm run dev
```

---

### 4. Notebook (Model Training)

```bash
cd ../notebook
jupyter notebook aflatoxin_model.ipynb
```

Use this notebook to:
- Preprocess grain quality data
- Train and evaluate the XGBoost model
- Export the trained model for FastAPI use

---

## 🧠 ML Model Overview

The system uses an **XGBoost** classifier with 300 decision trees, trained on 11 grain quality parameters. The model outputs classification probabilities and confidence scores for:

| Category     | Aflatoxin Level   |
|--------------|-------------------|
| Children     | ≤ 5 μg/kg         |
| Adults       | 5–20 μg/kg        |
| Animals      | 20–300 μg/kg      |
| Unsafe       | > 300 μg/kg       |

Preprocessing includes:
- Scaling
- Encoding
- Feature engineering

---

## 🔒 Authentication

FastAPI includes:
- JWT-based user authentication
- Role-based access control
- Secure route handling

---

## 📬 Notification System

Notifications are triggered for:
- High-risk classifications
- Procurement reminders
- System alerts

Channels:
- SMS
- Email

---

## 📊 Reporting System

The backend includes a reporting service for:
- Compliance monitoring
- Classification audit logs
- Exportable risk reports

---

## 💾 Data Layer

The backend uses:
- **PostgreSQL** for structured institutional and classification data
- **Redis** for session/prediction cache
- **File Storage** for model files, logs, and datasets
- **Automated Backups** for disaster recovery

---

## 📦 Dependencies

Install all Python dependencies:

```bash
pip install -r requirements.txt
```
