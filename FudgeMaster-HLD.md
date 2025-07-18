# FudgeMaster Web App: High-Level Design (HLD)

## 1. Overview
FudgeMaster is a modular, scalable web application for CBSE Class 11 and 12 Accountancy, designed for exam readiness and engaging learning. The HLD outlines the architecture, major modules, data flow, and integration points based on the SRS.

## 2. Architecture Diagram
- Layered architecture with clear separation of concerns:
  - Presentation Layer (Frontend)
  - Application Layer (Modules/Features)
  - Data Layer (Backend/Database)
- Modular folder/file structure:
  - /modules/class11/
  - /modules/class12/
  - /modules/mindmap/
  - /modules/transaction-simulation/
  - /modules/question-paper-review/
  - /modules/adaptive-feedback/
  - /modules/gamification/
  - /modules/accessibility/
  - /modules/table-formats/
  - /modules/continuous-improvement/
  - /rules/Accounting-Rules.md
  - /formats/Accounting-Book-Formats.md

## 3. Major Modules & Responsibilities
- **Class 11 & 12 Modules:** Content delivery, quizzes, revision, and progress tracking.
- **Mind Map Navigation:** Visual topic map, clickable nodes, links to modules.
- **Custom Transaction Simulation:** Transaction input, validation, feedback, progression through accounting stages.
- **Old Question Paper Review:** Access, attempt, and analyze previous years’ papers.
- **Adaptive Feedback:** Analyze performance, personalize revision paths, feedback messages.
- **Gamification:** XP, badges, leaderboards, streaks, daily challenges.
- **Voiceover & Chatbot:** Audio content, interactive Q&A, support.
- **Accessibility:** WCAG compliance, screen reader support, keyboard navigation.
- **Table Formats & Rules:** Render templates, validate entries, provide guidance.
- **Continuous Improvement:** Collect feedback, manage updates, changelog.

## 4. Data Flow & Integration
- **Frontend:**
  - Renders UI, receives user input, displays content and feedback.
  - Communicates with modules via RESTful APIs.
- **Modules:**
  - Each module is self-contained, with its own logic, UI components, and API handlers.
  - Modules reference rules and formats files for validation and rendering.
- **Backend:**
  - PostgreSQL database stores user data, progress, content, analytics.
  - APIs handle data exchange between frontend and backend.

## 5. External Interfaces
- **User Interface:** Responsive web UI, mind map, quizzes, dashboards.
- **Database:** PostgreSQL for persistent storage.
- **APIs:** RESTful endpoints for all module interactions.
- **Rules & Formats Files:** Referenced by modules for validation and template rendering.

## 6. Security & Scalability
- Secure authentication, encrypted data transfer.
- Modular design supports scaling and easy maintenance.
- Regular backups and error handling for reliability.

## 7. Accessibility & Engagement
- WCAG 2.1 compliance, keyboard navigation, high-contrast mode.
- Gamification features to motivate and engage users.

## 8. Summary
FudgeMaster’s HLD ensures a modular, maintainable, and scalable architecture, with clear separation of features, rules, and formats. All modules interact via APIs and reference dedicated files for rules and templates, supporting rapid revision, deep learning, and exam readiness.
