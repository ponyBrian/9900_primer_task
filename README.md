# COMP9900 Project Proposal - H16C_ALMOND Team

## 📄 Title Page

- **Course Code and Title**: COMP9900 Information Technology Project  
- **Project ID and Title**: Project 4 - A Database-Driven Platform For Pediatric Speech Therapy Progress Tracking  
- **Team Name**: H16C_ALMOND  
- **Team Alias**: MLP  
- **Team Members**:
  - Wenjing Wang - Scrum Master
  - Canxuan Gang - Product Owner
  - Xiaoyu Cao - Developer
  - Qianhui Huang - Developer
  - Wenyuan Zhao - Developer
  - Yangfangyuan Zhao - Developer
- **Submission Date**: 2025-06-18

---

## 📚 1. Background (15%)

### a. Problem Definition and Impact

Speech and language disorders are common among children worldwide. Early diagnosis and continuous therapy are crucial for improving children's communication skills. Speech-Language Pathologists (SLPs) work with children to provide tailored exercises and monitor their progress. 

Current tablet-based solutions like Say66 provide interactive training but lack comprehensive management tools for therapists. SLPs often struggle to manage case files, monitor detailed progress over time, and generate individualized reports.

This project proposes a **database-driven web platform** that allows SLPs to efficiently:
- Manage children profiles
- Design and assign customized exercises
- Monitor progress with phoneme-level data
- Generate reports that aid therapy planning

### b. Review of Existing Systems

| System | Strengths | Weaknesses |
|--------|-----------|------------|
| **Speech Blubs** | Engaging interface, gamification attracts children | Lacks therapist management tools and detailed reporting |
| **Say66 Tablet Game (current)** | Interactive exercises, pronunciation assessment, JSON data export | No backend for therapist management, no data aggregation, no centralized reporting |

By addressing these gaps, our solution enhances the clinical workflow, improves data utilization, and empowers SLPs with actionable insights.

---

## 🧩 2. User Stories and Sprints (25%)

### a. Scope Statement

> We will deliver a functional web-based system for SLPs to manage patients, create exercises, track detailed progress, and generate reports based on assessment data. The system includes a MySQL database, RESTful API backend (Flask or Node.js), React frontend, and Firebase integration for file storage. Tablet-side development and AI model development are out of scope.

**Client Approval**: Approved via email on 2025-06-15.

---

### b. Sprint 1 User Stories (Core Functionalities)

#### US-01: SLP Login & Authentication

- **As a** Speech Language Pathologist  
- **I want** to securely log in  
- **So that** I can access my assigned patients

- **Acceptance Criteria**:  
  - Secure password authentication with JWT
  - Error handling for invalid credentials
  - Session expiration handling

- **Story Points**: 3  
- **Priority**: High

#### US-02: View Assigned Children List

- **As a** SLP  
- **I want** to view a list of my assigned children  
- **So that** I can manage and track their progress

- **Acceptance Criteria**:  
  - Display child list with Name, Age, Level, and Last Update
  - Allow selection to view individual profile

- **Story Points**: 3  
- **Priority**: High

#### US-03: Add/Edit Child Profiles

- **As a** SLP  
- **I want** to create and update child profiles  
- **So that** I can maintain accurate patient information

- **Acceptance Criteria**:  
  - Form fields: Name, DOB, Initial Assessment Level
  - Update and delete existing records

- **Story Points**: 5  
- **Priority**: High

#### US-04: Create Exercises

- **As a** SLP  
- **I want** to select words and create exercises  
- **So that** I can customize training for each child

- **Acceptance Criteria**:  
  - Select words from Firebase database
  - Save exercise configurations

- **Story Points**: 5  
- **Priority**: Medium

#### US-05: Assign Exercise to Child

- **As a** SLP  
- **I want** to assign created exercises to children  
- **So that** they can practice assigned materials

- **Acceptance Criteria**:  
  - Select child, assign exercise, record assigned date
  - Allow marking as Initial Assessment

- **Story Points**: 5  
- **Priority**: Medium

---

### c. Product Backlog (Sprint 2 & 3 Features)

| User Story | Description | Story Points | Sprint |
|-------------|-------------|--------------|--------|
| US-06 | Display Exercise Progress Summary | 8 | Sprint 2 |
| US-07 | View Word Attempt History | 5 | Sprint 2 |
| US-08 | Generate Reports | 8 | Sprint 2 |
| US-09 | Phoneme-level Error Summary | 5 | Sprint 2 |
| US-10 | Admin Interface (SLP Management) | 5 | Sprint 3 |
| US-11 | Integration API for Tablet Upload | 8 | Sprint 3 |
| US-12 | Firebase File Linkage (Speech/JSON) | 5 | Sprint 3 |
| US-13 | Dashboard Visualization | 5 | Sprint 3 |

All product backlog stories will follow full Connextra format with Acceptance Criteria on Jira.

---

### d. Sprint Timeline and Milestones

| Sprint | Dates | Focus |
|--------|-------|-------|
| Sprint 1 | Week 3 → Week 5 | Core patient management, exercise creation, and assignment |
| Sprint 2 | Week 5 → Week 8 | Progress reporting, detailed analysis, and report generation |
| Sprint 3 | Week 8 → Week 10 | API integration, Firebase linkage, and final polish for demo |

---

## ⚙ 3. Technical Design (55%)

### a. System Architecture Diagram (Text Description)

- **Frontend** (React):
  - Login Page
  - Dashboard Page
  - Child Profile Management
  - Exercise Creation Page
  - Progress Visualization & Reports

- **Backend** (Flask/Node.js):
  - Authentication Service (JWT)
  - User Management Module
  - Exercise Management Module
  - Assignment Management Module
  - Progress Tracking Module
  - Report Generation Module

- **Database (MySQL):**
  - Tables for Users, Children, Exercises, Assignments, Progress Data, Phoneme Errors, Word Attempts

- **External Storage:**
  - Firebase Storage for speech files and assessment JSONs

- **APIs:**
  - RESTful API for frontend/backend communication
  - Tablet Upload API for assessment data submission

- **Security:**
  - JWT-based authentication, hashed passwords, access control

---

### b. Interface Storyboarding Suggestions

- **Login Screen:**  
  - Input fields: Email, Password  
  - Forgot Password link

- **Dashboard Screen:**  
  - List of assigned children  
  - Quick access to recent progress reports

- **Child Profile Screen:**  
  - Editable child info  
  - List of assigned exercises  
  - Progress summaries

- **Exercise Creation Screen:**  
  - Word selector (from Firebase)  
  - Save exercise to database

- **Progress Report Screen:**  
  - Table of exercises completed  
  - Word-level performance breakdown  
  - Phoneme error charts

Tools: Figma, Lucidchart

---

### c. Design Justifications

| Problem | Proposed Solution | Alternatives Considered | Reasoning |
|---------|--------------------|-------------------------|-----------|
| User Authentication | JWT with secure token | OAuth | Lightweight, stateless, secure |
| Database | MySQL | MongoDB | Structured data model fits relational schema |
| File Storage | Firebase | AWS S3 | Firebase already used by existing tablet system |
| Backend | Flask/Node.js | Django | Lightweight, faster development for API |
| Frontend | React | Vue.js | React flexible, large community support |

- The architecture avoids monolithic design by splitting business logic into service modules.
- Firebase integration minimizes unnecessary file duplication.
- RESTful APIs ensure future extensibility for mobile/tablet integration.

---

### d. Functionality Mapping

| Project Objective | User Stories | Notes |
|-------------------|--------------|-------|
| User Authentication | US-01 | Secure SLP login |
| Child Profile Management | US-02, US-03 | Manage children records |
| Exercise Creation & Assignment | US-04, US-05 | Customized exercises per child |
| Progress Tracking & Reports | US-06, US-07, US-08, US-09 | Aggregate phoneme-level data |
| Tablet Integration | US-11, US-12 | Data upload from tablet |
| Admin Features | US-10, US-13 | Dashboard & management |

---

## 📝 4. Report Formatting and Additional Requirements

- File format: PDF  
- Minimum 10 pages (excluding cover, TOC, references)  
- Font size ≤ 12pt  
- APA or Harvard referencing required  
- All Jira screenshots for user stories included

---

## 📖 5. References

- Say66 official website: https://say66.com/
- SuperDuper Publications: https://www.superduperinc.com/
- Agile Alliance. (2001). Agile Manifesto. http://agilemanifesto.org
- Cohn, M. (2005). Agile Estimating and Planning. Pearson Education.
- Relevant academic papers on pediatric speech therapy & database system design.

---
