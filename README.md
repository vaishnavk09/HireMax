HireMax – Explainable AI Hiring Tool

HireMax is an Applied AI full-stack system that helps recruiters screen and rank candidates against a job description using explainable, deterministic logic combined with AI-powered language understanding.

Unlike black-box resume screeners, HireMax focuses on transparency, control, and trust.

🎯 Problem Statement

Recruiters often receive hundreds of resumes for a single role.
Manual screening is slow, inconsistent, and biased, while many AI tools act as opaque black boxes.

HireMax solves this by:

Structuring resumes and job descriptions into clean data

Ranking candidates using deterministic, explainable scoring

Using AI only where it makes sense (language understanding), not decision-making

🧠 Core Principles

No black-box AI decisions

Deterministic and explainable scoring

Clear separation between application logic and AI logic

Production-style architecture, not a demo

🏗️ System Architecture
Frontend (React)
   |
   | REST APIs
   |
Backend (Node.js + Express)
   - Authentication (JWT)
   - Job Description Management
   - Resume Upload & Orchestration
   - Deterministic Scoring Engine
   |
PostgreSQL
   |
Python AI Service (FastAPI)
   - Resume Parsing (Gemini API)
   - Job Description Parsing
   - Interview Question Generation

Why this architecture?

Node.js handles auth, APIs, and business rules

Python isolates AI logic for clarity and scalability

AI is a supporting component, not the decision-maker

✨ Features (MVP)
Recruiter Workflow

Secure authentication (JWT)

Create and manage job descriptions

Upload multiple candidate resumes (PDF)

Automatically parse resumes into structured data

Rank candidates against a job description

View score breakdowns and explanations

Generate interview questions based on candidate gaps

🤖 AI Design (Important)
Where AI is used

Resume → structured JSON parsing

Job description → structured requirements

Interview question generation

Where AI is NOT used

Candidate scoring

Ranking

Final decision logic

Why?

To ensure:

Reproducibility

Explainability

Debuggability

Recruiter trust

📊 Scoring Strategy (Explainable)

Final candidate score is computed using a weighted deterministic formula:

Final Score =
  (Skill Match × Weight) +
  (Experience Match × Weight) +
  (Project Relevance × Weight)


Each component score is:

Computed using explicit rules

Stored in the database

Shown to the user with a breakdown

This avoids LLM randomness and bias.

🛠️ Tech Stack
Frontend

React

REST API integration

Backend

Node.js

Express

JWT Authentication

Database

PostgreSQL

AI Layer

Python (FastAPI)

Gemini API (language understanding only)

📁 Project Structure (High-Level)
HireMax/
├── client/        # React frontend
├── server/        # Node.js + Express backend
├── ai-service/    # Python FastAPI AI service
└── README.md

🚀 Getting Started (Local Setup)
Prerequisites

Node.js

Python 3.9+

PostgreSQL

Gemini API key

Backend
cd server
npm install
npm run dev

AI Service
cd ai-service
pip install -r requirements.txt
uvicorn app:app --reload

Frontend
cd client
npm install
npm start

🧪 Error Handling & Edge Cases

Invalid or unreadable resumes are marked as failed

AI parsing failures are safely handled and logged

Protected routes require valid JWT

Scoring only runs on successfully parsed data

📌 Current Status

✅ Project setup and architecture

✅ Authentication

⏳ Resume parsing

⏳ Scoring engine

⏳ Interview question generation

(Actively under development)

🎓 Why This Project?

This project was built to:

Learn applied AI system design

Practice production-style backend architecture

Understand where AI adds value and where it shouldn’t

Build a project that can be defended in technical interviews

👤 Author

Vaishnav Kedar
Applied AI & Full-Stack Developer
GitHub: https://github.com/vaishnavk09
