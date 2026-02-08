# 📁 PROJECT FOLDER STRUCTURE

## Complete Final Structure

```
AI Resume Analysis & Job Tracker/
│
├── .git/                           # Git version control (hidden)
├── .gitignore                      # Files to ignore in Git
├── README.md                       # Project documentation (public)
├── IMPLEMENTATION_PLAN.md          # Private (not pushed to GitHub)
├── PROJECT_EXECUTION_PLAN.md       # Private (not pushed to GitHub)
├── LICENSE                         # Private (not pushed to GitHub)
│
├── client/                         # FRONTEND (React)
│   ├── node_modules/               # Dependencies (ignored by git)
│   ├── public/                     # Static files
│   │   ├── favicon.ico
│   │   └── index.html
│   │
│   ├── src/                        # Source code
│   │   ├── assets/                 # Images, fonts, etc.
│   │   ├── components/             # Reusable UI components
│   │   │   ├── ui/                 # shadcn/ui components
│   │   │   │   ├── Button.jsx
│   │   │   │   ├── Input.jsx
│   │   │   │   ├── Card.jsx
│   │   │   │   └── ...
│   │   │   ├── layout/             # Layout components
│   │   │   │   ├── Header.jsx
│   │   │   │   ├── Footer.jsx
│   │   │   │   ├── Sidebar.jsx
│   │   │   │   └── Layout.jsx
│   │   │   └── features/           # Feature-specific components
│   │   │       ├── auth/
│   │   │       │   ├── LoginForm.jsx
│   │   │       │   ├── SignupForm.jsx
│   │   │       │   └── GoogleLoginButton.jsx
│   │   │       ├── ats/
│   │   │       │   ├── ResumeUploader.jsx
│   │   │       │   ├── JobDescriptionInput.jsx
│   │   │       │   ├── AnalysisResults.jsx
│   │   │       │   └── InterviewQuestions.jsx
│   │   │       ├── gallery/
│   │   │       │   ├── ResumeCard.jsx
│   │   │       │   ├── ResumeGrid.jsx
│   │   │       │   └── ResumePreview.jsx
│   │   │       └── tracker/
│   │   │           ├── ApplicationForm.jsx
│   │   │           ├── ApplicationList.jsx
│   │   │           ├── StatusBadge.jsx
│   │   │           └── DashboardStats.jsx
│   │   │
│   │   ├── pages/                  # Route pages
│   │   │   ├── Home.jsx
│   │   │   ├── Login.jsx
│   │   │   ├── Signup.jsx
│   │   │   ├── Dashboard.jsx
│   │   │   ├── Profile.jsx
│   │   │   ├── ATSChecker.jsx
│   │   │   ├── ResumeGallery.jsx
│   │   │   ├── JobTracker.jsx
│   │   │   └── NotFound.jsx
│   │   │
│   │   ├── hooks/                  # Custom React hooks
│   │   │   ├── useAuth.js
│   │   │   ├── useUser.js
│   │   │   ├── useToast.js
│   │   │   └── useDebounce.js
│   │   │
│   │   ├── context/                # React Context providers
│   │   │   ├── AuthContext.jsx
│   │   │   └── ThemeContext.jsx
│   │   │
│   │   ├── services/               # API calls
│   │   │   ├── api.js              # Axios instance
│   │   │   ├── authService.js
│   │   │   ├── atsService.js
│   │   │   ├── galleryService.js
│   │   │   └── trackerService.js
│   │   │
│   │   ├── utils/                  # Helper functions
│   │   │   ├── formatDate.js
│   │   │   ├── validateForm.js
│   │   │   └── constants.js
│   │   │
│   │   ├── App.jsx                 # Main App component
│   │   ├── main.jsx                # Entry point
│   │   └── index.css               # Global styles
│   │
│   ├── .env                        # Environment variables (ignored)
│   ├── .env.example                # Template for .env
│   ├── .eslintrc.json              # ESLint config
│   ├── .prettierrc                 # Prettier config
│   ├── package.json                # Dependencies & scripts
│   ├── pnpm-lock.yaml              # Lock file
│   ├── vite.config.js              # Vite configuration
│   └── tailwind.config.js          # Tailwind configuration
│
└── server/                         # BACKEND (Express)
    ├── node_modules/               # Dependencies (ignored by git)
    │
    ├── src/                        # Source code
    │   ├── config/                 # Configuration files
    │   │   ├── database.js         # MongoDB connection
    │   │   ├── cloudinary.js       # Cloudinary setup
    │   │   ├── email.js            # Resend/Nodemailer config
    │   │   └── gemini.js           # Google Gemini API
    │   │
    │   ├── models/                 # Mongoose schemas
    │   │   ├── User.js
    │   │   ├── Resume.js
    │   │   ├── Analysis.js
    │   │   └── Application.js
    │   │
    │   ├── controllers/            # Request handlers
    │   │   ├── authController.js
    │   │   ├── userController.js
    │   │   ├── atsController.js
    │   │   ├── galleryController.js
    │   │   └── trackerController.js
    │   │
    │   ├── services/               # Business logic
    │   │   ├── authService.js
    │   │   ├── atsService.js       # AI analysis logic
    │   │   ├── emailService.js
    │   │   └── uploadService.js
    │   │
    │   ├── middleware/             # Middleware functions
    │   │   ├── auth.js             # JWT verification
    │   │   ├── validation.js       # Input validation
    │   │   ├── errorHandler.js     # Error handling
    │   │   └── upload.js           # Multer config
    │   │
    │   ├── routes/                 # API routes
    │   │   ├── authRoutes.js
    │   │   ├── userRoutes.js
    │   │   ├── atsRoutes.js
    │   │   ├── galleryRoutes.js
    │   │   └── trackerRoutes.js
    │   │
    │   ├── utils/                  # Helper functions
    │   │   ├── logger.js           # Logging utility
    │   │   ├── responseFormatter.js
    │   │   ├── asyncHandler.js
    │   │   └── validators.js
    │   │
    │   ├── jobs/                   # Cron jobs
    │   │   └── reminderJob.js
    │   │
    │   └── server.js               # Entry point
    │
    ├── uploads/                    # Temporary uploads (ignored)
    ├── .env                        # Environment variables (ignored)
    ├── .env.example                # Template for .env
    ├── .eslintrc.json              # ESLint config
    ├── .prettierrc                 # Prettier config
    ├── package.json                # Dependencies & scripts
    └── pnpm-lock.yaml              # Lock file
```

---

## 📊 Folder Purpose Breakdown

### Root Level

| Folder/File | Purpose | Git Status |
|------------|---------|------------|
| `.git/` | Version control history | Tracked |
| `.gitignore` | Files to exclude from Git | Tracked |
| `README.md` | Public project documentation | Tracked |
| `client/` | Frontend React application | Tracked |
| `server/` | Backend Express application | Tracked |
| `IMPLEMENTATION_PLAN.md` | Private planning doc | **Ignored** |
| `PROJECT_EXECUTION_PLAN.md` | Private execution plan | **Ignored** |
| `LICENSE` | Proprietary license | **Ignored** |

---

### Client Folder (Frontend)

| Folder | Purpose | Why? |
|--------|---------|------|
| `public/` | Static assets served as-is | HTML, favicon, images |
| `src/assets/` | Build-time assets | Images, fonts compiled with app |
| `src/components/` | Reusable UI pieces | DRY principle - don't repeat code |
| `src/pages/` | Route-level components | Each route gets its own file |
| `src/hooks/` | Custom React hooks | Reusable stateful logic |
| `src/context/` | Global state providers | Auth state, theme, etc. |
| `src/services/` | API communication | Centralize all API calls |
| `src/utils/` | Helper functions | Pure functions, no side effects |

**Why this structure?**
- **Separation of Concerns**: Each folder has ONE job
- **Scalability**: Easy to add new features
- **Team Collaboration**: Multiple devs can work without conflicts
- **Testability**: Each piece can be tested independently

---

### Server Folder (Backend)

| Folder | Purpose | Why? |
|--------|---------|------|
| `config/` | External service configs | Database, APIs, email |
| `models/` | Database schemas | Data structure definitions |
| `controllers/` | Request handlers | Handle HTTP requests |
| `services/` | Business logic | Core functionality |
| `middleware/` | Request interceptors | Auth, validation, logging |
| `routes/` | API endpoints | Define URL paths |
| `utils/` | Helper functions | Reusable utilities |
| `jobs/` | Scheduled tasks | Cron jobs for reminders |

**Why this structure?**
- **MVC Pattern**: Model-View-Controller separation
- **Service Layer**: Business logic separate from HTTP
- **Testability**: Each layer can be unit tested
- **Real Companies**: This is how Airbnb, Uber, Netflix structure backends

---

## 🔄 Request Flow Example

### Example: User uploads resume for ATS check

**Frontend Flow:**
```
User action → Component (ResumeUploader.jsx)
           → Service (atsService.js - API call)
           → Axios instance (api.js)
```

**Backend Flow:**
```
API Request → Route (atsRoutes.js)
           → Middleware (auth.js - verify JWT)
           → Controller (atsController.js - handle request)
           → Service (atsService.js - business logic)
           → External API (Gemini AI)
           → Model (Analysis.js - save to database)
           → Response back to frontend
```

**Why this flow?**
- Each layer has a single responsibility
- Easy to debug (know exactly where to look)
- Easy to modify (change one layer without breaking others)

---

## 🎯 Key Principles

### 1. **Don't Repeat Yourself (DRY)**
- Reusable components in `components/`
- Shared logic in `hooks/` and `utils/`

### 2. **Separation of Concerns**
- UI logic ≠ Business logic ≠ Data logic
- Each layer independent

### 3. **Single Responsibility**
- Each file/folder does ONE thing well

### 4. **Scalability**
- Easy to add new features without refactoring
- New developer can onboard quickly

---

## 📝 Notes

### What Gets Committed to Git?

✅ **Committed (Public):**
- Source code (client/ and server/)
- README.md
- Configuration files (.eslintrc, etc.)
- .gitignore

❌ **NOT Committed (Private/Generated):**
- node_modules/ (dependencies)
- .env (secrets)
- uploads/ (temporary files)
- IMPLEMENTATION_PLAN.md (private)
- PROJECT_EXECUTION_PLAN.md (private)
- LICENSE (private)

### Why This Structure is Interview-Friendly?

When asked in interviews:

**"How did you structure your project?"**

You can confidently explain:
- ✅ MVC pattern on backend
- ✅ Component-based architecture on frontend
- ✅ Separation of concerns
- ✅ Service layer pattern
- ✅ Middleware chain

**This shows:**
- You understand **architecture**
- You follow **industry standards**
- You can work in **real teams**

---

## 🚀 Current Progress

Right now you have:
```
✅ client/ (empty)
✅ server/ (empty)
```

By end of Phase 0, you'll have:
```
✅ client/ (initialized with Vite + React)
✅ server/ (initialized with Express)
✅ package.json in both
✅ .env.example templates
✅ ESLint + Prettier configured
```

By end of entire project, you'll have the complete structure shown above! 🎯

---

**Next: Let's initialize the server with package.json!**
