# FudgeMaster Web App: Low-Level Design (LLD)

## 1. Overview
This LLD provides detailed specifications for each module, file structure, data models, API endpoints, and integration logic for the FudgeMaster web app.

## 2. File & Folder Structure
```
FudgeMaster/
├── modules/
│   ├── class11/
│   │   ├── BlahBlahBasics.js
│   │   ├── TightenTheScrews.js
│   │   └── BigYikes.js
│   ├── class12/
│   │   ├── PartnerPanic.js
│   │   ├── ShareSpinner.js
│   │   ├── RatioRazer.js
│   │   ├── YeetMaster.js
│   │   └── AdjustMania.js
│   ├── mindmap/
│   │   └── MindMap.js
│   ├── transaction-simulation/
│   │   └── TransactionSimulation.js
│   ├── question-paper-review/
│   │   └── QuestionPaperReview.js
│   ├── adaptive-feedback/
│   │   └── AdaptiveFeedback.js
│   ├── gamification/
│   │   └── Gamification.js
│   ├── accessibility/
│   │   └── Accessibility.js
│   ├── table-formats/
│   │   └── TableFormats.js
│   ├── continuous-improvement/
│   │   └── ContinuousImprovement.js
├── rules/
│   └── Accounting-Rules.md
├── formats/
│   └── Accounting-Book-Formats.md
├── assets/
│   └── images, diagrams, audio
├── db/
│   └── models.js
├── api/
│   └── endpoints.js
├── public/
│   └── index.html, styles.css
├── app.js
└── README.md
```

## 3. Module Details
### Class 11 & 12 Modules
- Each module exports functions for content delivery, quizzes, progress tracking, and sample questions.
- Example (BlahBlahBasics.js):
  - `getContent()`, `getQuiz()`, `trackProgress(userId)`

### Mind Map Navigation
- MindMap.js renders the mind map UI, handles node clicks, and links to modules.
- Functions: `renderMindMap()`, `navigateToNode(nodeId)`

### Custom Transaction Simulation
- TransactionSimulation.js handles transaction input, validation, feedback, and progression.
- Functions: `submitEntry(entry)`, `validateEntry(entry)`, `getFeedback(entry)`
- References rules from Accounting-Rules.md

### Old Question Paper Review
- QuestionPaperReview.js loads papers, tracks attempts, provides solutions and analytics.
- Functions: `loadPaper(year)`, `submitAnswer(answer)`, `getAnalysis(userId)`

### Adaptive Feedback
- AdaptiveFeedback.js analyzes performance, generates feedback, and suggests revision paths.
- Functions: `analyzePerformance(userId)`, `generateFeedback(userId)`

### Gamification
- Gamification.js manages XP, badges, leaderboards, streaks, and challenges.
- Functions: `awardXP(userId, points)`, `updateLeaderboard()`, `trackStreak(userId)`

### Voiceover & Chatbot
- Accessibility.js provides audio content and chatbot Q&A.
- Functions: `playAudio(contentId)`, `chatbotQuery(query)`

### Table Formats & Rules
- TableFormats.js renders templates, validates entries, and provides guidance.
- Functions: `renderTemplate(type)`, `validateTableEntry(entry)`
- References Accounting-Book-Formats.md

### Continuous Improvement
- ContinuousImprovement.js collects feedback, manages updates, and changelog.
- Functions: `submitFeedback(userId, feedback)`, `getChangelog()`

## 4. Data Models (db/models.js)
- User: { id, name, email, password, progress, xp, badges }
- Quiz: { id, module, questions, answers, userResponses }
- Transaction: { id, userId, stage, entry, feedback }
- QuestionPaper: { id, year, questions, solutions }
- Feedback: { id, userId, message, date }

## 5. API Endpoints (api/endpoints.js)
- `/api/user/register` (POST)
- `/api/user/login` (POST)
- `/api/content/:module` (GET)
- `/api/quiz/:module` (GET/POST)
- `/api/transaction/submit` (POST)
- `/api/question-paper/:year` (GET/POST)
- `/api/feedback/submit` (POST)
- `/api/gamification/leaderboard` (GET)

## 6. Integration Logic
- Modules interact via API calls and shared data models.
- Rules and formats files are imported for validation and rendering.
- UI components are dynamically loaded based on navigation and user actions.

## 7. Security & Accessibility
- All sensitive data is encrypted and securely stored.
- Accessibility.js ensures WCAG compliance and user-friendly navigation.

## 8. Summary
This LLD provides a detailed blueprint for implementing the FudgeMaster web app, ensuring modularity, maintainability, and scalability. Each feature and section is isolated in its own file/module, with clear data models and API contracts for integration.
