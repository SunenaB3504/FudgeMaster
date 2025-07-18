# FudgeMaster Web App: Software Requirements Specification (SRS)

## 1. Introduction
FudgeMaster is a highly modular, gamified web application for CBSE Class 11 and 12 Accountancy. It is designed for exam readiness, conceptual mastery, and engaging learning experiences. The app will be built with a modular architecture, with separate files for each feature, section, and functionality.

## 2. Overall Description
- **Target Users:** CBSE Class 11 & 12 students, teachers, and tutors.
- **Platform:** Web (responsive, desktop/laptop priority).
- **Tech Stack:** HTML, JavaScript, CSS (frontend); PostgreSQL (backend).
- **Design Principle:** Highly modular, maintainable, and scalable.

## 3. Functional Requirements
### 3.1 Modular Structure
- Each major feature, section, and functionality will reside in a separate file/module.
- Modules will communicate via well-defined interfaces/APIs.

### 3.2 Content Modules
- **Class 11 Modules:**
  - Blah Blah Basics (Theoretical Framework)
  - Tighten the Screws (Accounting Process, Terms, Rules, Subsidiary Books)
  - Big Yikes (Ledger, Trial Balance, Error Rectification, Bank Reconciliation, Depreciation, Financial Statements)
- **Class 12 Modules:**
  - The Real Grind (PartnerPanic, ShareSpinner, RatioRazer, YeetMaster, AdjustMania)

### 3.3 Mind Map Navigation
- Visual mind map with clickable nodes for each topic/subtopic.
- Each node links to its own module file.

### 3.4 Custom Transaction Simulation
- Separate module for transaction input, validation, feedback, and progression through accounting stages.

### 3.5 Old Question Paper Review
- Module for accessing, attempting, and analyzing previous years’ CBSE question papers.

### 3.6 Adaptive Feedback
- Module for analyzing student performance and providing personalized feedback and revision paths.

### 3.7 Engagement & Accessibility
- Gamification (XP, badges, leaderboards, streaks, daily challenges) in a dedicated module.
- Voiceover and chatbot features in separate modules.
- Accessibility features (WCAG compliance, screen reader support) in a dedicated module.

### 3.8 Table Formats & Rules
- Module for standardized accounting book templates and sample filled tables.

### 3.9 Continuous Improvement
- Module for collecting user feedback, issue reporting, and update management.

## 4. Non-Functional Requirements
- **Scalability:** Support for large user base and modular expansion.
- **Security:** Secure authentication, encrypted data transfer, privacy compliance.
- **Reliability:** High availability, regular backups, error handling.
- **Accessibility:** WCAG 2.1 compliance, keyboard navigation, high-contrast mode.
- **Maintainability:** Modular codebase, clear documentation, version control.

## 5. External Interfaces
- **User Interface:** Responsive web UI, mind map navigation, quizzes, dashboards.
- **Database:** PostgreSQL for user data, progress, content, and analytics.
- **APIs:** RESTful APIs for module communication and data exchange.

## 6. System Architecture
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
- Each module contains its own logic, UI components, and API handlers.
- All accounting rules and book formats are maintained in dedicated files and referenced by relevant modules for validation, guidance, and template rendering.

## 7. Summary
FudgeMaster will be a modular, scalable, and engaging web app for CBSE Accountancy, supporting rapid revision, deep learning, and exam readiness. All features, sections, and functionalities will be implemented as separate modules/files for maintainability and future growth.

## 8. Rules and Formats Modules
- All accounting rules and book formats are maintained in separate, dedicated files:
  - `Accounting-Rules.md`: Contains comprehensive accounting rules for each section/module, strictly aligned with CBSE requirements.
  - `Accounting-Book-Formats.md`: Contains standardized templates for all key accounting books and statements.
- These files are referenced by relevant modules for validation, guidance, and template rendering.
- Modular separation ensures easy updates, maintenance, and compliance with syllabus changes.
