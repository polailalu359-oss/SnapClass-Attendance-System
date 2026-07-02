# SnapClass 🎓

**AI-Powered Facial Recognition Attendance System**

SnapClass is a smart, contactless attendance management system that uses facial recognition and voice authentication to automate classroom attendance. Built for educational institutions, it eliminates manual roll calls and proxy attendance through biometric verification.

🔗 **Live Demo:** [snapclass-polailalu359.streamlit.app](https://snapclass-polailalu359.streamlit.app)

---

## 🚀 Features

- **Facial Recognition Attendance** — Students mark attendance by simply looking at the camera
- **Voice-Based Attendance (Optional)** — Alternate authentication method using voice enrollment
- **Teacher Portal** — Create subjects, manage enrolled students, view attendance analytics
- **Student Portal** — Self-enroll in subjects, view personal attendance history and stats
- **Secure Authentication** — Password hashing with bcrypt for teacher accounts
- **Real-Time Database** — Powered by Supabase (PostgreSQL) for reliable data storage
- **Attendance Analytics** — Session counts, attendance percentage, and subject-wise tracking

---

## 🛠️ Tech Stack

| Category | Technology |
|---|---|
| Frontend | Streamlit |
| Backend / Database | Supabase (PostgreSQL) |
| Authentication | bcrypt (password hashing) |
| Facial Recognition | face_recognition / OpenCV |
| Voice Processing | Voice embedding pipeline |
| Language | Python |

---

## 📸 How It Works

1. **Teacher** creates an account and sets up subjects/sections
2. **Students** enroll by capturing their face (and optionally, voice) for biometric registration
3. During class, students mark attendance via the camera — the system matches their face against stored embeddings
4. Attendance is logged in real-time and visible to both teachers and students through their respective dashboards

---

## 📂 Project Structure

```
SnapClass/
├── app.py                     # Main application entry point
├── src/
│   ├── components/            # Reusable UI components & dialogs
│   ├── database/               # Supabase client & database operations
│   ├── pipelines/               # Face & voice recognition pipelines
│   ├── screens/                 # Teacher & Student screen logic
│   └── ui/                      # Layout components
├── .streamlit/
│   └── secrets.toml             # Environment configuration (not committed)
└── requirements.txt
```

---

## ⚙️ Setup & Installation

1. **Clone the repository**
   ```bash
   git clone https://github.com/your-username/SnapClass.git
   cd SnapClass
   ```

2. **Create a virtual environment**
   ```bash
   python -m venv venv
   venv\Scripts\activate
   ```

3. **Install dependencies**
   ```bash
   pip install -r requirements.txt
   ```

4. **Configure Supabase**
   - Create a free project at [supabase.com](https://supabase.com)
   - Create a `.streamlit/secrets.toml` file (this file is git-ignored and never committed) with:
     ```toml
     SUPABASE_URL = "your-project-url"
     SUPABASE_KEY = "your-anon-key"
     ```

5. **Run the app**
   ```bash
   streamlit run app.py
   ```

> ⚠️ **Note:** No API keys or credentials are stored in this repository. Each user must configure their own Supabase project and keys locally.

---

## 🎯 Key Learnings

This project involved solving real-world engineering challenges including:
- Designing a normalized relational database schema (students, subjects, enrollments, attendance logs)
- Integrating a third-party facial recognition pipeline with a live database
- Debugging API-level errors (schema caching, column mismatches) in a production PostgREST backend
- Building a dual-portal (Teacher/Student) authentication and authorization flow
- Deploying and managing a live application on Streamlit Cloud

---

## 📊 Database Schema

| Table | Description |
|---|---|
| `teachers` | Teacher accounts (username, hashed password, name) |
| `students` | Student records with face & voice embeddings |
| `subjects` | Subjects/sections created by teachers |
| `subject_student` | Enrollment mapping (many-to-many) between students and subjects |
| `attendance_logs` | Attendance records with timestamp and presence status |

---

## 👤 Author

**Lalu Prasad Polai**
BCA Graduate (Berhampur University, CGPA 8.8) | Pursuing MCA in AI & ML, BPUT
📍 Odisha, India
[LinkedIn](#) • [GitHub](#)

---

## 📄 License

This project is open source and available under the [MIT License](LICENSE).
