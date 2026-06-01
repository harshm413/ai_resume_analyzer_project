# AI Resume Analyzer

An AI-powered resume analysis tool that scores resumes against job descriptions, provides ATS compatibility feedback, and suggests improvements. Upload a PDF resume, enter a job description, and get instant AI-driven feedback.

## Features

- **PDF Resume Upload** — Drag-and-drop or click to upload resume files
- **Job-Specific Analysis** — Scores resume against a specific job title and description
- **ATS Score** — Rates how well the resume passes Applicant Tracking Systems
- **AI Feedback** — Detailed improvement suggestions powered by Claude 3.7 Sonnet
- **Resume History** — View and compare past analyses
- **Cloud Storage** — Resumes stored securely via Puter.js cloud platform

## Tech Stack

- **Frontend**: React 19, React Router 7, TypeScript, Tailwind CSS
- **AI**: Claude 3.7 Sonnet (via Puter.js AI API)
- **Storage**: Puter.js (cloud filesystem + key-value store)
- **PDF Processing**: pdfjs-dist (PDF to image conversion for AI analysis)
- **State Management**: Zustand
- **Build**: Vite

## How It Works

```
User uploads PDF → PDF converted to image → Uploaded to Puter cloud storage
     ↓
User enters job title + description → AI prompt constructed
     ↓
Claude 3.7 Sonnet analyzes resume against job requirements
     ↓
Returns: ATS score, section-by-section feedback, improvement suggestions
```

## Running Locally

```bash
npm install
npm run dev
```

Open [http://localhost:5173](http://localhost:5173)

## Architecture

- `app/routes/upload.tsx` — Main upload form and analysis trigger
- `app/routes/resume.tsx` — Results display with scores and feedback
- `app/lib/puter.ts` — Puter.js SDK wrapper (auth, filesystem, AI, key-value store)
- `app/lib/pdf2img.ts` — PDF to image conversion
- `constants/index.ts` — AI prompt instructions and scoring criteria
