SentriAI – Early Dropout Prediction

SentriAI is an AI-driven system that helps educational institutions predict and reduce early student dropout rates through predictive analytics and targeted interventions.

---

## Table of Contents

- [Overview](#overview)
- [Vision & Mission](#vision--mission)
- [Problem Statement](#problem-statement)
- [Goals & Success Metrics](#goals--success-metrics) 
- [Target Users](#target-users)
- [Core MVP Scope](#core-mvp-scope)
- [Features](#features)
- [Architecture (High-Level)](#architecture-high-level)
- [Getting Started](#getting-started)
- [Usage](#usage)
- [Data & Privacy](#data--privacy)
- [Roadmap](#roadmap)
- [Contributing](#contributing)
- [Team](#team)
- [License](#license)

---

## Overview

SentriAI analyzes student data such as academic performance, attendance, and engagement to predict the likelihood that a student will drop out. It exposes an educator-facing dashboard with risk scores, alerts, and recommended interventions so institutions can support at-risk students early and improve overall retention.

> Status: **MVP – in planning / early development**

---

## Vision & Mission

**Vision:**  
Reduce student dropout rates through predictive analytics and targeted support.

**Mission:**  
Provide educators with actionable insights to identify and assist at-risk students as early as possible.

---

## Problem Statement

High student dropout rates:

- Reduce institutional funding
- Damage institutional reputation
- Negatively impact student success

Most institutions rely on lagging indicators (e.g., exam failures, repeated absences) and manual processes. This leads to delayed or inconsistent interventions.

SentriAI addresses this by:

- Providing **early and accurate** dropout risk predictions
- Automating identification of at-risk students
- Supporting **proactive** and structured interventions

---

## Goals & Success Metrics

### High-Level Goals

- Reduce student dropout rates
- Improve retention across cohorts / programs
- Increase student engagement

### Key Performance Indicators (KPIs)

- **Dropout rate reduction (%)**
- **Prediction accuracy (%)** (e.g., precision/recall on at-risk classification)
- **Intervention effectiveness (%)** (e.g., % at-risk students who stay enrolled after intervention)

---

## Target Users

- **Educators:** Teachers, lecturers, professors who interact with students daily
- **Administrators:** Deans, department heads, and academic program leads
- **Counselors:** Academic and student support counselors

### Example Persona

**Name:** Professor Anya Sharma  
**Role:** University Professor  

**Goals:**

- Help students succeed
- Identify struggling students early
- Improve overall engagement

**Pain Points:**

- Limited time for 1:1 student follow-up  
- Hard to spot at-risk students before it’s “too late”  
- Little or no data-driven insight to guide interventions

SentriAI gives her a dashboard with risk scores, alerts, and suggested interventions so she can focus her limited time where it matters most.

---

## Core MVP Scope

The MVP focuses on the essential pieces needed for early dropout prediction and intervention:

1. **Data Integration**
   - Secure connection to Student Information Systems (SIS)
   - Secure connection to Learning Management Systems (LMS)

2. **Predictive Modeling**
   - Machine learning model to estimate dropout risk per student
   - Configurable thresholds for what counts as “at-risk”

3. **Dashboard**
   - List and search of students with current risk scores
   - Individual student profiles with key factors contributing to risk
   - Simple visualizations for educators (e.g., risk level badges)

4. **Intervention Recommendations**
   - Evidence-based suggestions linked to student risk profile
   - Recommendations that educators and counselors can act on quickly

The MVP will be piloted with a selected group of students and faculty to gather feedback and refine the system.

---

## Features

### 1. Data Integration

- Secure ingestion of:
  - Academic data (grades, assessments, progress)
  - Attendance records
  - LMS engagement signals (logins, assignment submissions, quiz activity, etc.)
- Support for periodic batch sync or API-based integration (implementation detail up to the project stack)

**Priority:** High  

---

### 2. Risk Score Calculation

- Generates a dropout risk score for each student using a machine learning model
- Utilizes multiple factors (academic, attendance, engagement, etc.)
- Supports “at-risk” labeling for quick filtering and alerting

**Priority:** High  

---

### 3. Dashboard Visualization

- Web-based dashboard for educators and administrators
- Key capabilities:
  - View all students with risk levels (e.g., low/medium/high)
  - Filter and search by course, cohort, or risk status
  - Drill down into student profiles with contributing factors

**Priority:** High  

---

### 4. Alert System

- Notifications when a student’s risk score crosses a threshold or spikes significantly
- Different alert views for:
  - Individual educators (for their classes/students)
  - Counselors / central support teams

**Priority:** Medium  

---

### 5. Intervention Recommendations

- Suggests targeted, evidence-based interventions for each at-risk student
  - E.g., “Schedule 1:1 meeting”, “Recommend tutoring”, “Send check-in email”
- Designed to be practical and easy to apply within an educator’s existing workflow

**Priority:** Medium  

---

### 6. Reporting & Analytics

- Aggregated reporting on:
  - Dropout trends over time
  - Intervention uptake and effectiveness
  - Cohort/program-level risk distributions
- Helps institutions evaluate the impact of SentriAI over time

**Priority:** Low (Post-MVP enhancement)  

---

## Architecture (High-Level)

> Note: This section is intentionally technology-agnostic so it can fit different stacks (Python, Node.js, etc.). Adapt it to match the actual implementation.

A typical deployment could include:

- **Data Layer**
  - Connectors/ETL jobs pulling from SIS & LMS
  - Central database for student profiles, risk scores, and intervention logs

- **ML / Analytics Layer**
  - Training pipeline for dropout risk model
  - Inference service that computes risk scores on a schedule or on demand

- **API Layer**
  - REST or GraphQL API exposing:
    - Student list + risk scores
    - Student profiles & history
    - Alerts and interventions

- **Frontend**
  - Web dashboard for educators, admins, and counselors
  - Authentication & authorization (role-based access)

---

## Getting Started

> This is a template section. Update the stack-specific commands once the tech stack is finalized.

### Prerequisites

- Git
- A recent version of Node.js / Python / [your chosen stack]
- Access credentials or sample data for SIS / LMS integration (or mock data)

### Installation

```bash
# Clone the repository
git clone https://github.com/<org-or-user>/sentri-ai.git
cd sentri-ai

# Install dependencies (example – replace with real commands)
# Node.js
npm install
# or
# Python
# pip install -r requirements.txt
```

### Configuration

1. Copy the example environment file:

   ```bash
   cp .env.example .env
   ```

2. Fill in the environment variables for:

   - Database connection
   - SIS / LMS API keys or connection strings
   - Authentication / JWT secrets
   - Any model or storage configuration

---

## Usage

> Update this once you have concrete scripts/commands.

- **Run the development server**

  ```bash
  # Example – replace with your actual dev command
  npm run dev
  ```

- **Run the API/Backend only**

  ```bash
  # Example – replace with your actual backend command
  npm run start:api
  ```

- Navigate to `http://localhost:3000` (or your configured port) to access the SentriAI dashboard.

---

## Data & Privacy

SentriAI handles sensitive student data. Any implementation should:

- Comply with local and institutional data protection regulations
- Use secure transport (HTTPS) and encryption at rest where applicable
- Restrict access via role-based permissions (educators see only relevant students)
- Log access to student data for audit and compliance

---

## Roadmap

Short-term (MVP):

- [ ] Finalize MVP requirements with stakeholders
- [ ] Implement data integration with at least one SIS and one LMS
- [ ] Build and validate first dropout risk model
- [ ] Implement educator dashboard with risk scores and basic student profiles
- [ ] Add simple alerting for high-risk students
- [ ] Pilot with a small group of students & faculty; collect feedback

Mid-term:

- [ ] Expand intervention recommendation engine
- [ ] Add reporting & analytics module
- [ ] Improve model performance and fairness across different groups
- [ ] Add support for additional SIS/LMS providers

Long-term:

- [ ] Multi-institution support and benchmarking
- [ ] Advanced cohort analysis & forecasting
- [ ] Self-service configuration for institutions (thresholds, intervention templates, etc.)

---

## Contributing

Contributions are welcome!  

1. Fork the repository  
2. Create a feature branch: `git checkout -b feature/my-feature`  
3. Commit your changes: `git commit -m "Add my feature"`  
4. Push the branch: `git push origin feature/my-feature`  
5. Open a Pull Request with a clear description of your changes

Please ensure your code follows any existing style guides and includes relevant tests.

---

## Team

Core project team:

- Ruth Igwe-Oruta  
- Maureen Cheptoo  
- Olatunji Abdulraheem  
- Idara Akpan  
- Akpakpa Rukevwe Mary  
- Asheson Enneh  
- Eno Peters  
- Vivian Ibeawuchi  
- Nissi Marshall  
- Precious Babalola Umar Oghenerukevwe  

(If this is an open-source repo, you can also add maintainers and contributors here.)

---

## License

Specify your license here, for example:
This project is licensed under the **MIT License** – see the [LICENSE](LICENSE) file for details.
