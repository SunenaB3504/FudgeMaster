## Software Requirements Specification (SRS) for FinFlow: The Gen-Z Accounting Navigator

**Version:** 1.0
**Date:** July 18, 2025

### 1. Introduction

#### 1.1 Purpose
This document comprehensively specifies the functional and non-functional requirements for "FinFlow," a web-based interactive accounting learning application. It is meticulously designed for Class 11th and 12th standard CBSE students in India. The primary goal is to transform traditional accounting learning into an engaging, effective, and intuitive experience through interactive modules, a full accounting cycle simulation, and a Gen-Z-centric user interface. This SRS serves as the foundational blueprint for the application's development, design, and testing.

#### 1.2 Scope
FinFlow will encompass the entire CBSE Accountancy syllabus for both Class 11th and 12th standards. This includes:
* **Class 11:** Theoretical Framework, Accounting Process (Journal, Ledger, Trial Balance, Subsidiary Books, Bank Reconciliation Statement), Depreciation, Provisions & Reserves, Financial Statements of Sole Proprietorship (with adjustments).
* **Class 12:** Accounting for Partnership Firms (Fundamentals, Reconstitution, Dissolution), Accounting for Companies (Share Capital, Debentures), Analysis of Financial Statements (Comparative, Common Size, Ratios), and Cash Flow Statement (Indirect Method).

The application will feature interactive learning modules, practice problems, a full accounting cycle simulation ("Transaction Cruncher"), and dedicated exam preparation tools. It will be accessible via web browsers on desktops/laptops and mobile devices, supporting cloud-based user authentication and data storage for seamless progress tracking.

#### 1.3 Target Audience
The primary user is a CBSE Class 11th or 12th standard student (typically aged 15-18) in India. This demographic is characterized by a strong familiarity with digital interfaces, a preference for visual and interactive content, immediate feedback, and gamified learning experiences.

#### 1.4 Definitions and Acronyms
* **CBSE:** Central Board of Secondary Education
* **SRS:** Software Requirements Specification
* **UI:** User Interface
* **UX:** User Experience
* **HTML:** HyperText Markup Language
* **CSS:** Cascading Style Sheets
* **JS:** JavaScript
* **ES6+:** ECMAScript 2015 and later versions of JavaScript
* **BaaS:** Backend-as-a-Service
* **CRUD:** Create, Read, Update, Delete
* **RLS:** Row Level Security
* **P&L:** Profit & Loss
* **J.F.:** Journal Folio
* **L.F.:** Ledger Folio
* **CFS:** Cash Flow Statement
* **XP:** Experience Points (Gamification)
* **TL;DR:** Too Long; Didn't Read (Gen-Z slang)
* **IRL:** In Real Life (Gen-Z slang)
* **GST:** Goods and Services Tax

---

### 2. Overall Description

#### 2.1 Product Perspective
FinFlow is a web-based educational application. It will operate as a standalone platform hosted in the cloud, utilizing a Backend-as-a-Service (BaaS) for all server-side functionalities, data management, and user authentication.

#### 2.2 User Characteristics
Users are digitally native, expecting intuitive interfaces and quick responses. They are accustomed to visual learning, short-form content, and gamified progress. They need clear, jargon-minimized explanations, but also the option for deeper dives. The app must cater to diverse learning paces and provide adaptive feedback.

#### 2.3 General Constraints
* **Technology Stack:** Frontend built with HTML, CSS, and JavaScript (ES6+).
* **Backend:** Supabase for PostgreSQL database, authentication, and API layer.
* **Hosting:** Frontend hosted on a static site hosting service (e.g., Netlify, Vercel, Firebase Hosting); backend managed by Supabase.
* **Cross-Browser Compatibility:** Full functionality and consistent user experience across modern web browsers (Chrome, Firefox, Safari, Edge) on desktop, laptop, and mobile devices.
* **CBSE Syllabus Adherence:** All curriculum content, problem types, formatting rules, and terminology must strictly align with the current CBSE Accountancy syllabus for Classes 11th and 12th. This includes specific formats for financial statements, adjustments, and ratio calculations.
* **Accessibility:** Adherence to basic accessibility standards for web content (e.g., proper semantic HTML, keyboard navigation, sufficient color contrast).
* **Offline Capability (Future Enhancement):** Initial release will require internet connectivity.

#### CBSE Rules and Formats (Detailed)
**Class 11:**
- Journal Entries: Date | Particulars | L.F. | Debit | Credit. Golden Rules of Debit & Credit (Personal, Real, Nominal accounts). Narration required.
- Ledger: Account Name | Date | Particulars | J.F. | Debit | Credit. Posting from Journal/Subsidiary Books, balancing at period end.
- Trial Balance: Account Name | Debit Balance | Credit Balance. Total debits must equal total credits.
- Financial Statements (Sole Proprietorship): Trading Account (Opening Stock, Purchases, Direct Expenses, Sales, Closing Stock), Profit & Loss Account (Indirect Expenses, Indirect Incomes), Balance Sheet (Assets, Liabilities, Capital, Loans, Creditors). Adjustments: Outstanding/Prepaid, Accrued/Received in Advance, Depreciation, Bad Debts, Provisions.
- Subsidiary Books: Cash Book (Single/Double/Triple column), Petty Cash Book (Simple/Analytical/Imprest), Purchases/Sales Book (CBSE format), GST columns (CGST, SGST, IGST) where applicable.
- Error Rectification: Identify error type (omission, commission, principle, compensating). Rectify before/after trial balance as per CBSE guidelines.

**Class 12:**
- Partnership Accounts: Capital Accounts (Fixed/Fluctuating), P&L Appropriation Account (Interest on Capital/Drawings, Salary, Commission, Profit Sharing), Goodwill Calculation (Average Profit, Super Profit, Capitalization), Revaluation Account (asset/liability revaluation), Dissolution (Realisation Account, Partners’ Capital, Cash/Bank Account).
- Company Accounts: Share Issue (journal entries for issue at par/premium/discount, forfeiture, re-issue), Debenture Issue (journal entries, interest calculation), Financial Statements (Vertical format as per Schedule III, Companies Act, 2013).
- Financial Analysis: Comparative Statement (Year 1 vs Year 2, amount and percentage change), Common Size Statement (all items as % of base), Ratio Calculation (formula, interpretation, CBSE-specified ratios).
- Cash Flow Statement: Indirect Method (start with Net Profit, adjust for non-cash/non-operating items, changes in working capital), format for Operating, Investing, Financing Activities.
- Adjustments: All adjustments (outstanding, prepaid, accrued, received in advance, depreciation, bad debts, provisions, interest, commission) must be shown as per CBSE rules in statements.

---

### 3. Functional Requirements (What the App Will Do)

#### 3.1 User Management & Authentication
* **FR1.1 User Registration:** Users shall be able to register an account using email/password or social login options (e.g., Google).
* **FR1.2 User Login:** Users shall be able to log in to their registered account.
* **FR1.3 Password Management:** Users shall be able to initiate and complete forgotten password resets.
* **FR1.4 Session Management:** The system shall maintain user sessions securely, allowing users to return to their last progress point.
* **FR1.5 Profile Management:** Users shall be able to view their overall progress, XP, achievements, and basic profile information.

#### 3.2 Content & Learning Modules
* **FR2.1 Class Selection:** Upon initial login or via a prominent menu, users shall select "Class 11th" or "Class 12th" to load the respective curriculum and interface.
* **FR2.2 Interactive Mind Map (Central Navigation):**
    * **FR2.2.1 Node Representation:** Each accounting concept or major topic shall be represented as an interactive, clickable node.
    * **FR2.2.2 Expand/Collapse:** Tapping a node shall expand its sub-branches, and tapping again or elsewhere shall collapse it.
    * **FR2.2.3 Zoom & Pan:** Users shall be able to intuitively pinch-to-zoom and pan across the mind map using standard gestures.
    * **FR2.2.4 "Quick Explainer" (11th Std Default):** Tapping a concept node shall open a full-screen overlay featuring:
        * "TL;DR" (1-2 sentences concise summary).
        * "How It Works" (simple explanation, potentially with a small animation).
        * "IRL Example" (real-world analogy).
        * "Pro Tip!" (a practical hint or common pitfall).
    * **FR2.2.5 "Deep Dive Hub" (12th Std Default):** Tapping a topic node shall open a dedicated hub with navigable tabs:
        * "Quick Recap": Hyper-condensed bullet points, key formulas, and rules for rapid revision.
        * "Solved Walkthroughs": Interactive step-by-step solutions to CBSE-level past year problems.
        * "Practice Arena": Access to sets of exam-style problems.
        * "Mistake Gallery": Displays common errors related to the specific topic with explanations.
    * **FR2.2.6 Navigation Cues:** Clear breadcrumbs or similar visual cues to indicate the current location within the mind map hierarchy.

* **FR2.3 Core Theory & Concepts:**
    * **FR2.3.1 Definition Display:** Provide precise, CBSE-aligned definitions for all accounting terms, principles, and concepts.
    * **FR2.3.2 Analogies & Examples:** Integrate Gen-Z relatable analogies and practical examples for better comprehension.
    * **FR2.3.3 Visual Aids:** Utilize infographics, diagrams, and short animations to explain complex ideas.
* **FR2.4 Standard-Specific Content Adherence (CBSE Syllabus):**
    * **FR2.4.1 Class 11th Content:**
        * **Theoretical Framework:** Accounting meaning, objectives, advantages/limitations, users, qualitative characteristics, basic terms (Assets, Liabilities, Capital, Drawings, Revenue, Expense, etc.), Accounting Equation, Golden Rules of Debit & Credit, Fundamental Assumptions, Accounting Concepts & Principles (all CBSE specified), Systems of Accounting (Cash/Accrual).
        * **Accounting Process:** Vouchers, Source Documents, Journal (simple, compound entries), Subsidiary Books (Cash Book: simple, double column; Petty Cash Book: simple, analytical, imprest; Purchases/Sales Book, Purchases/Sales Return Book, Bills Receivable/Payable Book, Journal Proper). **Integration of simple GST calculations (CGST, SGST, IGST) in relevant entries.** Ledger (format, posting, balancing). Trial Balance (meaning, objectives, preparation by balance method). Rectification of Errors (simple errors, before TB, after TB but before final accounts).
        * **Bank Reconciliation Statement:** Meaning, reasons for difference, preparation.
        * **Depreciation, Provisions & Reserves:** Meaning, purpose, methods of depreciation (SLM, WDV), distinction between provisions/reserves, types of reserves.
        * **Financial Statements of Sole Proprietorship:** Trading Account, Profit & Loss Account, Balance Sheet (grouped and marshalled), including all CBSE-specified adjustments (Closing Stock, Outstanding/Prepaid, Accrued/Income received in advance, Depreciation, Bad Debts, Provision for Doubtful Debts, Provision for Discount on Debtors/Creditors, Abnormal Loss, Goods for personal use/staff welfare, Interest on Capital, Manager's Commission).
    * **FR2.4.2 Class 12th Content:**
        * **Accounting for Partnership Firms:** Features, Partnership Deed, Provisions of Indian Partnership Act 1932 (in absence of deed), Fixed vs. Fluctuating Capital, P&L Appropriation Account (Interest on Capital/Drawings, Salary, Commission, Profit Sharing, Guarantee), Past Adjustments.
        * **Goodwill:** Meaning, nature, factors, methods of valuation (Average Profit, Super Profit, Capitalization).
        * **Reconstitution of Partnership:** Change in Profit Sharing Ratio (Sacrificing/Gaining Ratio), Admission of a Partner (Goodwill treatment, Revaluation A/c, Partners' Capital A/cs, New PSR, Old/New Balance Sheet), Retirement/Death of a Partner (Calculation of amount due, Loan A/c/Executor's A/c), Dissolution of Partnership Firm (Realisation A/c, Partners' Capital A/cs, Cash/Bank A/c – *excluding piecemeal distribution, sale to company, insolvency*).
        * **Accounting for Companies:** Features/Types of Companies, Shares (equity/preference), Share Capital types, Issue of Shares (par, premium, discount), Calls in Arrears/Advance (excluding interest), Issue for consideration other than cash, Private Placement, ESOP, Sweat Equity, Forfeiture & Re-issue, Disclosure in Balance Sheet. Debentures (Issue at par/premium/discount, other than cash, terms of redemption, Interest on Debentures).
        * **Financial Statements of a Company:** **Vertical Format** of Balance Sheet (as per Schedule III, Companies Act, 2013) and Statement of Profit & Loss.
        * **Analysis of Financial Statements:** Meaning, Significance, Purpose, Limitations. Tools: Comparative Statements, Common Size Statements.
        * **Accounting Ratios:** Meaning, Objectives, Classification & Computation (Liquidity: Current, Quick; Solvency: Debt-Equity, Total Assets to Debt, Proprietary, Interest Coverage; Activity: Inventory Turnover, Trade Receivables Turnover, Trade Payables Turnover, Working Capital Turnover; Profitability: Gross Profit, Operating Ratio, Operating Profit Ratio, Net Profit Ratio, Return on Investment/Capital Employed, Earnings Per Share (if relevant to CBSE scope), Dividend Per Share, Price Earning Ratio).
        * **Cash Flow Statement:** Meaning, Objectives, Benefits, Cash & Cash Equivalents, Classification of Activities, Preparation (CBSE specific **Indirect Method** focus for Operating Activities).

#### 3.3 Transaction Processing Engine ("Transaction Cruncher")
* **FR3.1 Transaction Input:** Users shall be able to input transactions using a guided form with dropdowns and text fields.
* **FR3.2 Journalizing Module:**
    * **FR3.2.1 Guided Entry:** Users input Date, select Debit/Credit Accounts (from chart of accounts), enter amounts, and provide narration.
    * **FR3.2.2 Debit/Credit Balance Validation:** Real-time validation ensures debit total equals credit total for each entry.
    * **FR3.2.3 Subsidiary Book Option:** For Class 11, users can opt to process transactions through a selected Subsidiary Book (Cash Book, etc.), with automatic ledger posting.
* **FR3.3 Ledger Posting Module:**
    * **FR3.3.1 Automated Posting:** The system shall automatically transfer entries from Journal/Subsidiary Books to respective Ledger accounts.
    * **FR3.3.2 Interactive Ledger View:** Displays each Ledger account in standard T-format or columnar format, showing running balances.
    * **FR3.3.3 Cross-Referencing:** Clicking a Journal entry highlights its corresponding Ledger entry(s), and vice-versa (simulating J.F./L.F.).
* **FR3.4 Trial Balance Generation Module:**
    * **FR3.4.1 Auto-Generation:** System automatically compiles a Trial Balance from final Ledger balances.
    * **FR3.4.2 Balance Validation:** Instantly checks if total debits equal total credits, with clear error flags if not.
* **FR3.5 Adjusting Entries Module:**
    * **FR3.5.1 Guided Adjustment Input:** Users are prompted to enter details for all relevant adjustments based on the problem context.
    * **FR3.5.2 Adjustment Journalizing:** System guides creation and posting of Adjustment Entries to Ledgers.
    * **FR3.5.3 Adjusted Trial Balance:** Generates an Adjusted Trial Balance incorporating all adjustments.
* **FR3.6 Financial Statement Generation Module:**
    * **FR3.6.1 Automated Preparation:** System automatically prepares:
        * Trading Account (Sole Prop)
        * Profit & Loss Account (Sole Prop)
        * Profit & Loss Appropriation Account (Partnership)
        * Statement of Profit and Loss (Company, Vertical Format)
        * Balance Sheet (Sole Prop: Horizontal; Partnership/Company: Vertical as per Schedule III)
    * **FR3.6.2 Interactive Statement View:** Line items shall be clickable, showing source from Trial Balance or specific adjustment details.
    * **FR3.6.3 CBSE Format Adherence:** Strictly follow CBSE-prescribed formats and groupings.
* **FR3.7 Cash Flow Statement Generation Module:**
    * **FR3.7.1 Method Selection:** Users select "Indirect Method" for CFS generation.
    * **FR3.7.2 Automated Creation:** System generates CFS (Operating, Investing, Financing Activities) using data from P&L Statement and Balance Sheet.
    * **FR3.7.3 Reconciliation Explanation:** For Indirect Method, visually explains reconciliation of Net Profit to Cash from Operations.
    * **FR3.7.4 Line-Item Detail:** Clicking on CFS lines provides details of contributing accounts/transactions.
* **FR3.8 Partnership Reconstitution/Dissolution Calculators (Specific to 12th Std):**
    * **FR3.8.1 Goodwill Calculator:** Tool to calculate goodwill using specified methods (Average Profit, Super Profit, Capitalization).
    * **FR3.8.2 Revaluation Account Builder:** Guided module for preparing Revaluation A/c entries and final balance.
    * **FR3.8.3 Partner's Capital Account Manager:** Auto-updates partner capital/current accounts based on transactions and appropriations.
    * **FR3.8.4 Realisation Account Builder:** Guided module for preparing Realisation A/c for dissolution.
* **FR3.9 Company Accounts Processors (Specific to 12th Std):**
    * **FR3.9.1 Share Issue/Forfeiture/Re-issue Simulator:** Guided input for share transactions, auto-generating Journal Entries and Ledger impacts. Includes calculation of forfeiture amount and re-issue profit/loss.
    * **FR3.9.2 Debenture Issue Calculator:** Guided input for debenture issue, including interest calculation.
* **FR3.10 Financial Statement Analysis Tools (Specific to 12th Std):**
    * **FR3.10.1 Comparative & Common Size Statements:** Users input 2 years of financial data; the app generates the statements with percentage changes.
    * **FR3.10.2 Ratio Calculator:** Users select a ratio, input required figures; the app calculates and provides an explanation of the ratio's significance.

#### 3.4 Practice & Assessment
* **FR4.1 Mini Quizzes ("Level Up Check"):** Short, interactive multiple-choice or T/F quizzes integrated after concept explanations. Immediate feedback provided.
* **FR4.2 Practice Problems ("Practice Arena"):** Curated sets of exam-style problems ranging in difficulty.
    * **FR4.2.1 Hint System:** Contextual hints available (may "cost" XP).
    * **FR4.2.2 Detailed Solutions:** Step-by-step solutions revealed after user attempt.
    * **FR4.2.3 Self-Assessment:** Users can mark their attempt quality ("Got it right," "Almost," "Struggled").
* **FR4.3 Timed Drills:** Option to practice specific problem types or sets under timed conditions.
* **FR4.4 Mock Exams ("Mock Exam Central"):** Full-length, timed mock tests simulating CBSE Board exam conditions (past papers, sample papers).
    * **FR4.4.1 Automatic Scoring:** For objective and short-answer sections.
    * **FR4.4.2 Marking Schemes/Sample Answers:** For subjective questions, provide detailed marking schemes and ideal answers for self-evaluation.

#### 3.5 Progress Tracking & Gamification
* **FR5.1 Concept Completion Tracking:** Visual indicators (e.g., "Peacock Feather Tick" icons) on mind map nodes for completed concepts/quizzes.
* **FR5.2 Progress Bars:** Visual progress bars for chapter/module completion within the dashboard.
* **FR5.3 XP System:** Users earn Experience Points (XP) for completing lessons, answering quizzes correctly, solving problems, and taking mock exams.
* **FR5.4 Performance Dashboard:** A central dashboard displaying overall progress, XP gained, average quiz scores, accuracy rates, and time spent.
* **FR5.5 "Weak Zone Locator":** Identifies and highlights specific sub-topics or concepts where the user consistently struggles or scores low, with direct links to relevant practice.
* **FR5.6 Achievements/Badges:** Award digital badges for milestones (e.g., "Journaling Master," "Trial Balance Wizard," "Full Syllabus Conqueror").

#### 3.6 Voiceover (Audio) Integration
* **FR6.1 Voiceover Playback:** Voiceovers shall narrate key concept explanations, definitions, walkthrough steps, and feedback messages.
* **FR6.2 User Controls:** Users shall be able to toggle voiceovers ON/OFF, adjust volume, and control playback speed (e.g., 0.75x, 1x, 1.25x).
* **FR6.3 Contextual Playback:** Voiceovers shall be triggered automatically upon entering a concept explanation or interaction, with a "Repeat" button.
* **FR6.4 Voiceover Persona:** The voiceover shall be a young, energetic, and relatable male/female voice with a conversational tone, consistent with Gen-Z aesthetics.

#### 3.7 Class 11 "Power Review" Module
* **FR7.1 Timed Session:** A dedicated module for a ~60-minute rapid review of Class 11 concepts with a visible countdown timer.
* **FR7.2 "Flashcard Flipper":** Presents concepts as concise digital flashcards (front: concept name, back: TL;DR definition/formula/example).
* **FR7.3 "Rapid Explainer" Overlay:** Short (10-15 second) animated overlays for each concept.
* **FR7.4 "Blitz Checks":** Very quick True/False, MCQs (2-3 options), or simple drag-and-drop quizzes after small batches of concepts.
* **FR7.5 "Quick Drill" Formats:** Simplified, rapid practice for Journal Entry identification, Ledger effects, and Trial Balance classification.
* **FR7.6 Review Queue:** Automatically adds concepts where the user struggles during the review for later focused practice.
* **FR7.7 Post-Review Summary:** Displays performance, time taken, and "Your Focus Areas."

---

### 4. Non-Functional Requirements (How the App Will Perform)

#### 4.1 Performance
* **NFR4.1.1 Responsiveness:** The UI shall render and respond to user interactions (taps, swipes, zooms, pans) within 100ms.
* **NFR4.1.2 Loading Times:** Initial application load shall complete within 5 seconds on a standard broadband connection. Individual module loads (e.g., opening a problem set, generating a financial statement) shall complete within 2-3 seconds.
* **NFR4.1.3 Processing Speed:** Calculation-intensive tasks (e.g., generating a full set of financial statements from 50+ transactions) shall complete within 5 seconds.

#### 4.2 Usability (UI/UX)
* **NFR4.2.1 Intuitive Navigation:** Navigation shall be highly intuitive, requiring minimal user training.
* **NFR4.2.2 Clear Feedback:** The system shall provide clear, immediate, and understandable feedback for all user actions and system states (e.g., success messages, error alerts, loading indicators).
* **NFR4.2.3 Consistency:** All UI elements, terminology, interaction patterns, and visual design (fonts, colors, icons) shall be consistent throughout the application.
* **NFR4.2.4 Readability:** Text content shall be highly readable with appropriate font sizes, line spacing, and sufficient color contrast. A dark/light mode toggle shall be provided.
* **NFR4.2.5 Gen-Z Aesthetics:** The UI/UX shall reflect modern Gen-Z preferences: clean, sleek, vibrant but minimalist color palette, engaging animations, and relatable visual language.
* **NFR4.2.6 Mobile-First Design:** The application shall be optimized for mobile devices as the primary target, ensuring excellent usability on smaller screens.

#### 4.3 Reliability
* **NFR4.3.1 Data Integrity:** All user progress data, practice attempts, scores, and settings stored in the database shall be accurate, consistent, and secure against corruption.
* **NFR4.3.2 Error Handling:** The application shall gracefully handle anticipated errors (e.g., network disconnections, invalid user input) and provide user-friendly error messages rather than crashing.
* **NFR4.3.3 Data Backup:** The underlying BaaS (Supabase) shall provide robust data backup and recovery mechanisms.

#### 4.4 Security
* **NFR4.4.1 User Authentication & Authorization:** User credentials shall be securely stored (hashed passwords) and transmitted (via HTTPS). Authentication shall leverage Supabase's built-in system. Row Level Security (RLS) in PostgreSQL shall ensure users can only access and modify their own data.
* **NFR4.4.2 Data Encryption:** All data transmitted between the client and server shall be encrypted using HTTPS/SSL/TLS protocols.
* **NFR4.4.3 Protection Against Common Vulnerabilities:** The application shall be designed and developed to mitigate common web security vulnerabilities (e.g., XSS, SQL injection, CSRF).

#### 4.5 Maintainability
* **NFR4.5.1 Modular Codebase:** The codebase shall be organized into logical, reusable modules and components (e.g., using Web Components, ES Modules) to facilitate easier updates and feature additions.
* **NFR4.5.2 Clean Code Practices:** Code shall be well-documented, adhere to coding standards, and be easily understandable by other developers.
* **NFR4.5.3 Scalability:** The architecture (Frontend + Supabase BaaS) should support future scaling to accommodate a growing user base without significant re-architecture.

#### 4.6 Portability & Cross-Platform Compatibility
* **NFR4.6.1 Web-Based Access:** The application shall be accessible via a standard web browser from any device (desktop, laptop, tablet, smartphone) with an internet connection.
* **NFR4.6.2 Responsive Design:** The UI shall adapt seamlessly to various screen sizes and orientations.
* **NFR4.6.3 Data Synchronization:** User data and progress shall synchronize in real-time across all devices where the user logs in.

---

### 5. Future Enhancements (Out of Scope for Initial Release)

* **Offline Mode:** Allowing access to pre-downloaded content and practice without active internet connection.
* **AI-Powered Tutoring/Hint System:** More sophisticated, adaptive hints and personalized learning paths.
* **Collaborative Study Features:** Options for users to connect with friends, share notes, or work on problems together.
* **Custom Problem Creation:** Allowing users (or teachers/admins) to create and share their own practice problems.
* **PDF Export:** Functionality to export generated financial statements or practice solutions to PDF.
* **Video Integration:** Embedding short conceptual video tutorials.
* **Gamification Leaderboards:** Competitive elements among users.
* **Teacher/Parent Dashboard:** Separate interface for monitoring student progress (with consent).

---