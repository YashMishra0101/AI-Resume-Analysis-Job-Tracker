# 🚧 AI-Powered Resume Analysis & Job Tracking System

> **Status:** 🔨 Work in Progress

An all in one AI powered platform that helps candidates manage their job search in a simple and organized way. It combines smart AI resume analysis, job application tracking and a Resume Gallery where users can explore and learn from real resumes, all in one place, so job seekers do not have to manage multiple tools.

---

## 🧑‍💻 CORE FEATURES

### Quick Overview of MVP

|  | Feature | Description |
|---|---------|-------------|
| 1 | **ATS Resume Checker** | Upload PDF, paste JD/role, AI analysis, Score, Suggestions + Interview Questions |
| 2 | **Resume Gallery** | Share resumes/templates, view others, like & filter |
| 3 | **Job Tracker** | Track applications, stats, reminders |

---

## 🛠️ TECH STACK

### Quick Overview

| Category | Technologies |
|---|---|
| **Frontend** | React 19, Vite, SWC, TailwindCSS, shadcn/ui, React Router v7, TanStack Query, Axios, React Hook Form, Zod, React Hot Toast, Phosphor Icons |
| **Backend** | Node.js, Express, JWT, argon2, Multer, pdf-parse, node-cron, Nodemailer |
| **AI** | Google Gemini API (Free: 15 req/min) |
| **Database** | MongoDB Atlas + Mongoose |
| **Storage** | Cloudinary |
| **Email** | Resend |
| **Hosting** | Vercel (Frontend) + Render (Backend) |

---

## 🔐 FOUNDATION: USER AUTHENTICATION & PROFILE

### Signup Options

**Email + Password**
User enters Name, Email, Password. Account created. Verification email sent. After verification → Main landing page.

**Google Login**
One-click signup/login using Google OAuth. No password needed. Account linked to Google profile.

**Guest Mode**
Try the app without signup. **Only ATS Resume Checker feature is available.** Other features require full account.

### Login
- Email + Password OR Google OAuth
- JWT tokens (Access + Refresh)
- Redirect to the main page after successful verification

---

## 👤 FOUNDATION: PROFILE MANAGEMENT

After signup or login, users can manage their profile:

### Profile Settings
- **Update Name** — Change display name anytime
- **Upload Profile Image** — Upload or change profile picture (JPG/PNG, max 2MB)
- **Change Email** — Update email address (requires verification of new email)
- **Password Management** — Change password (only for email/password accounts, not OAuth users)

All profile changes are saved to MongoDB and reflected immediately across the app.

---

## 📄 FEATURE 1: ATS RESUME CHECKER

### How It Works
1. User uploads resume **(PDF only, max 5MB)**
2. User enters job details in text box:
   - **Paste job description** from company website, OR
   - **Write what kind of job** they are looking for (e.g., "Frontend developer role with React and TypeScript")
3. AI analyzes resume based on user input using Gemini API
4. Shows results

### Analysis Results
- **ATS Score** (0-100)
- **Keyword Match %**
- **Section Scores** (Skills, Experience, Education, Formatting)
- **ATS Formatting Check** — Analyzes font consistency, header structure, and warns about complex graphics that confuse ATS.
- **Matched Keywords** — Keywords found in resume
- **Missing Keywords** — Keywords NOT in resume
- **Issues Found** — Problems with severity (Error/Warning/Info)
- **Improvement Suggestions** — Specific tips to improve
- **Personalized Interview Questions** — Top 10–50 questions (users can customize and select the exact number of questions they want) based on their resume, including experience, tech stack, and projects

---

## 🌐 FEATURE 2: Resume Gallery

### What It Is
A social platform where users share their resumes or resume templates publicly for inspiration and visibility.
*Users have full control over visibility and can optional anonymize personal details.*
**Benefit:** Job seekers can learn from successful resumes, find templates to improve their own, and showcase their work to potential recruiters.

### Uploading Resume
- Upload PDF resume

### Browsing Resumes
- View grid of public resumes
- Filter by: Most Liked / Newest
- Click to preview resume
- Like resumes others find helpful
- View uploader's profile
- Each resume card shows uploader's avatar + name
- Click to visit their profile
- See all their public resumes

---

## 📊 FEATURE 3: JOB TRACKER

### Adding Application
- Company Name
- Job Title
- Job URL (optional)
- Applied Date
- Status
- Notes

### Application Status Options
- 📝 Applied
- 👀 Viewed
- 📞 Interview Scheduled
- 💻 Technical Round
- 👔 HR Round
- ✅ Offer
- ❌ Rejected
- ⏸️ On Hold
- 🚫 Withdrawn

### Email Reminders (Optional)
- User can **choose to set a reminder** for any application
- User selects reminder time (24 hours before, 1 hour before, or custom)
- Email sent at the selected time
- Email includes: Company, Role, Time, Notes

### Dashboard Stats
- Total applications
- Applications this month
- Success rate and rejection rate (Interviews / Applications)

---

## 🛠️ TECH STACK — Deep Dive

### 📦 Package Manager

**pnpm**
A fast, disk-efficient package manager that uses hard links to save significant disk space. It performs faster than npm and enforces strict dependency management.

### ⚛️ Frontend

**React 19 + Vite + SWC**
Latest React version for building the user interface. Vite + SWC ensures instant server start and lightning-fast builds using native ESM.

**TailwindCSS 4 + shadcn/ui**
Tailwind v4 offers a highly optimized engine for styling directly in HTML. shadcn/ui provides accessible, reusable components that I copy into the codebase for full control.

**React Router v7 + TanStack Query**
Router v7 handles complex routing with improved type safety. TanStack Query v5 automates data fetching, caching, and background server-state synchronization.

**React Hook Form + Zod + Axios**
Hook Form manages complex forms with minimal re-renders, while Zod ensures rigorous schema validation. Axios handles HTTP requests with built-in interceptors.

**React Hot Toast**
Lightweight toast notification library for displaying success, error, and info messages. Simple API with beautiful default styling and full customization options.

**Phosphor Icons**
Flexible icon family with 6000+ icons in multiple weights (thin, light, regular, bold, fill). Provides consistent, high-quality icons for all UI elements.

### 🖥️ Backend

**Node.js + Express**
Event-driven architecture for running JS on the server. Express provides a minimal, flexible framework for building APIs and managing middleware.

**JWT + argon2**
Stateless authentication using secure JSON Web Tokens. argon2 is a memory-hard hashing algorithm significantly more secure than bcrypt against brute-force attacks.

**Multer + pdf-parse + node-cron**
Multer handles file uploads, `pdf-parse` extracts text from resume PDFs for AI, and `node-cron` schedules automated interview email reminders.

### 🤖 AI & Data

**Google Gemini API**
Google's AI model that reads resumes and suggests answers.
* **Free:** The system gets 15 requests per minute for free (enough for this project).
* **Paid:** Only if thousands of users hit it instantly.

**MongoDB Atlas + Mongoose**
Database to save user data and stats.
* **Free:** 512MB storage is free forever (enough for 10,000+ users).
* **Paid:** Only if the app stores huge amounts of data.

### ☁️ Infrastructure

**Cloudinary**
Where the app saves profile photos and resume PDFs.
* **Free:** The platform gets 25GB of storage/bandwidth per month.
* **Paid:** Only if there are tons of HD images/videos.

**Resend (via Nodemailer)**
Service to send emails (like "Verify account").
* **Free:** 3,000 emails per month (100 per day).
* **Paid:** Only if the app sends more than 3,000 emails/month.

**Vercel + Render**
Where the website lives on the internet.
* **Vercel (Frontend):** Free for personal projects.
* **Render (Backend):** Free tier available. The server automatically pauses to save resources after 15 minutes of inactivity (it wakes up automatically when a user visits).
* **Paid:** Only if 24/7 uptime without pausing is needed.


---

## 📝 Note

This project is built for learning, job preparation, and portfolio purposes.
The repository is public so recruiters and peers can review my work and
development progress.
