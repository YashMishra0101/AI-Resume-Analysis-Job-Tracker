# AI-Powered Resume Analysis & Job Tracking System

> **🚧 Status: Work in Progress**
> This project is actively under development. Features, UI, and documentation are being built and refined.⭐Star the repo to follow along.

An all-in-one AI-powered platform that helps job seekers manage their entire job search, from resume optimization to application tracking, in one place.

---

## 🧐 The Problem

Job seekers juggle multiple tools: one for resume feedback, another for tracking applications and random templates scattered across the internet. There's no single platform that combines **AI-driven resume analysis**, **application tracking** and **resume inspiration** into a unified experience.

## 💡 The Solution

This platform brings everything together:

- **Upload your resume** → Get instant AI-powered ATS scoring, keyword analysis and personalized interview questions
- **Track your applications** → Monitor status, set email reminders and view dashboard stats
- **Browse real resumes** → Learn from others, find inspiration and share your own

---

## ✨ Core Features

### 📄 ATS Resume Checker
Upload your resume (PDF) and paste a job description — the AI analyzes your resume and returns:
- **ATS Score** (0–100) with section-wise breakdown
- **Keyword Match** — matched vs missing keywords
- **Formatting Check** — flags ATS-unfriendly elements
- **Improvement Suggestions** — actionable tips to boost your score
- **Interview Questions** — 10–50 personalized questions based on your resume

### 🌐 Resume Gallery
A community-driven space where users share resumes publicly for inspiration:
- Browse, preview, and like resumes
- Filter by Most Liked or Newest
- View uploader profiles and their public resumes

### 📊 Job Application Tracker
Keep every application organized in one dashboard:
- Track company, role, status, dates, and notes
- 9 status stages (Applied → Interview → Offer/Rejected)
- **Email reminders** for upcoming interviews
- Dashboard stats: total apps, monthly activity, success rate

### 🔐 Authentication
- Email/Password signup with email verification
- Google OAuth (one-click login)
- Guest Mode — try the ATS checker without signing up

---

## 🛠️ Tech Stack

| Layer | Technologies |
|-------|-------------|
| **Frontend** | React 19, Vite, SWC, TailwindCSS 4, shadcn/ui, React Router v7, TanStack Query, React Hook Form, Zod, Axios |
| **Backend** | Node.js, Express, JWT (Access + Refresh), argon2, Multer, pdf-parse, node-cron |
| **AI** | Google Gemini API |
| **Database** | MongoDB Atlas + Mongoose |
| **Testing** | Vitest, React Testing Library, Supertest |
| **Storage** | Cloudinary (images + PDFs) |
| **Email** | Resend (via Nodemailer) |
| **Hosting** | Vercel (Frontend) · Render (Backend) · UptimeRobot (Keep-Alive) |

---

## 🏗️ Architecture

```
Frontend (React)  →  Backend (Express API)  →  MongoDB Atlas
                           ↓
                    Google Gemini API (AI Analysis)
                    Cloudinary (File Storage)
                    Resend (Email Service)
```

**Backend Pattern:** Route → Controller → Service → Model

- Controllers handle HTTP (thin layer)
- Services contain business logic (testable)
- Models define database schemas

**Frontend Pattern:** Feature-based module structure

- Each feature (auth, resume-checker, job-tracker) is self-contained
- Components, hooks, services, and pages grouped by feature

---

## 📁 Project Structure

```
ai-resume-job-tracker/
├── client/                    # React + Vite frontend
│   └── src/
│       ├── components/        # Shared UI components
│       ├── features/          # Feature modules (auth, resume, jobs)
│       ├── hooks/             # Global custom hooks
│       ├── lib/               # Axios, query client, utilities
│       ├── routes/            # Route definitions
│       └── __tests__/         # Frontend tests
│
├── server/                    # Express backend
│   ├── src/
│   │   ├── config/            # DB, Cloudinary, OAuth, env validation
│   │   ├── controllers/       # Route handlers
│   │   ├── middlewares/       # Auth, validation, rate limiting
│   │   ├── models/            # Mongoose schemas
│   │   ├── routes/            # API route definitions
│   │   ├── services/          # Business logic + AI integration
│   │   ├── utils/             # Helpers (logger, error classes)
│   │   └── validations/       # Zod schemas
│   └── __tests__/             # Backend tests (integration + unit)
│
├── .gitignore
└── README.md
```

---

## 🔒 Security

This project implements production-level security practices:

- **argon2** password hashing (stronger than bcrypt)
- **JWT** with HttpOnly cookies (prevents XSS token theft)
- **Access + Refresh token** rotation
- **Zod** schema validation on all inputs
- **Helmet.js** security headers
- **express-rate-limit** for API protection
- **Multer** file type/size restrictions

---

## ️ Roadmap

- [x] Project planning & architecture design
- [ ] Project foundation setup
- [ ] User authentication (Email + Google OAuth)
- [ ] Profile management + Cloudinary integration
- [ ] ATS Resume Checker with Gemini AI
- [ ] Resume Gallery (upload, browse, like)
- [ ] Job Application Tracker with dashboard
- [ ] Email reminders (node-cron + Resend)
- [ ] Guest mode
- [ ] Testing (Vitest + Supertest)
- [ ] Deployment (Vercel + Render)

---

## 👨‍💻 Author

**Yash Mishra**

- GitHub: [@YashMishra0101](https://github.com/YashMishra0101)
- LinkedIn: [Yash Mishra](https://www.linkedin.com/in/yash-mishra-356280223/)
- X (Twitter): [@YashRKMishra1](https://x.com/YashRKMishra1)

---

> This project is built for learning, job preparation and portfolio purposes. The repository is public so recruiters and peers can review my work and development progress.
