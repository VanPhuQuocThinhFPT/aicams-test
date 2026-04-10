# Software Requirements Specification

## AI Camera System

| Field | Value |
|-------|-------|
| **Project** | AI Camera System |
| **Group** | GROUP-01 |
| **Authors** | Hoang NM, Thanh Vien 1 |
| **Supervisors** | Giang Vien A |
| **Date** | 2026-04-07 |

---

## 1. Introduction

### 1.1 Purpose

This document describes the complete software requirements for the Student Management System (SMS). It is intended for the development team, project supervisors, and all relevant stakeholders.

### 1.2 Scope

The Student Management System is a web application that manages student information, grades, schedules, and notifications. Goal: Digitize management processes, reducing manual processing time by 80%. Out of scope: Financial management, facility management.

> **Topic Description**: AI Camera System

### 1.3 Definitions, Acronyms, and Abbreviations

| Term | Definition |
|------|------------|
| SRS | Software Requirements Specification |
| API | Application Programming Interface |
| JWT | JSON Web Token — A compact token format for secure authentication |
| RBAC | Role-Based Access Control — Access control model based on user roles |
| CRUD | Create, Read, Update, Delete — Basic data operations |
| UI/UX | User Interface / User Experience |
| REST | Representational State Transfer — Architectural style for designing APIs |
| CI/CD | Continuous Integration / Continuous Deployment |


### 1.4 References

1. IEEE 830-1998 - Recommended Practice for SRS
2. ISO/IEC/IEEE 29148:2018 - Requirements Engineering
3. FPT University Capstone Project Guidelines v2.0

### 1.5 Overview

This document consists of 5 main sections: (1) Introduction - purpose and scope; (2) Overall Description - architecture and constraints; (3) Detailed Requirements - functional and non-functional; (4) Verification Plan; (5) Appendixes.

## 2. Overall Description

### 2.1 Product Perspective

The system is a module within the FPT Education ecosystem, integrating with: (1) FAP - the existing academic management system, (2) Google Workspace - email and calendar services, (3) Payment Gateway - tuition fee processing.

### 2.2 Product Functions

The system provides the following major functions:

1. **Init Spring Boot 3 & Postgres** — Setup
2. **Authentication Module Deployment** — Detailed description for Authentication Epic
3. **Contribution Evaluation Algorithm** — Calculate the work efficiency score of each project member
4. **Setup Sprint Management Module** — Management descriptions
5. **Jira Webhook Integration System** — Build modules to connect and automatically receive data from Jira via Webhook
6. **Dashboard and Overview Reports** — Progress tracking interface for stakeholders
7. **Git/GitHub Sync Management** — Features related to fetching source code information and commit history
8. **Contribution Evaluation Algorithm** — Calculate the work efficiency score of each project member
9. **Dashboard and Overview Reports** — Progress tracking interface for stakeholders
10. **Authentication Module Deployment** — Detailed description for Authentication Epic
11. **Setup Sprint Management Module** — Management descriptions
12. **Jira Webhook Integration System** — Build modules to connect and automatically receive data from Jira via Webhook
13. **Git/GitHub Sync Management** — Features related to fetching source code information and commit history
14. **Authentication Module Deployment** — Detailed description for Authentication Epic
15. **Setup Sprint Management Module** — Management descriptions
16. **Jira Webhook Integration System** — Build modules to connect and automatically receive data from Jira via Webhook
17. **Git/GitHub Sync Management** — Features related to fetching source code information and commit history
18. **Contribution Evaluation Algorithm** — Calculate the work efficiency score of each project member
19. **Dashboard and Overview Reports** — Progress tracking interface for stakeholders

In addition to the EPICs already defined, the system also supports: PDF/Excel report generation, automated email notifications, and a real-time statistics dashboard for administrators.

### 2.3 Product Constraints

- Language: Java 17+ (Spring Boot 3.x), React 18+
- Database: PostgreSQL 15+
- Deployment: Docker containers on AWS/Azure
- Browser Support: Chrome, Firefox, Edge (latest 2 versions)
- Compliance: PDPA (Personal Data Protection Act)

### 2.4 User Characteristics

1. Admin (5 users): System administrators, advanced IT skills, full access to all features
2. Lecturers (50 users): Manage classes and grades, intermediate IT skills
3. Students (2000 users): View personal information, register courses, basic IT skills

### 2.5 Assumptions and Dependencies

- Users have a stable internet connection (minimum 1 Mbps)
- Server uptime is at least 99.5%
- The current FAP API will remain unchanged during development
- Student data is provided in CSV/Excel format

### 2.6 Apportioning of Requirements

Sprint 1-2: Authentication, User Management (Core)
Sprint 3-4: Course Registration, Schedule Management
Sprint 5-6: Grade Management, Reporting
Sprint 7-8: Notification System, Dashboard, Testing & Bug fixes

## 3. Requirements

### 3.1 External Interfaces

#### 3.1.1 User Interfaces

- Responsive web design (Desktop + Mobile)
- Follows Material Design 3 guidelines
- Dark mode support
- Languages: Vietnamese (default), English

#### 3.1.2 Hardware Interfaces

No special hardware requirements. The system runs entirely on cloud infrastructure.

#### 3.1.3 Software Interfaces

1. FAP API v2.0 (REST) - Synchronize student and course data
2. Google OAuth 2.0 - User authentication via FPT accounts
3. SendGrid API - Email notification delivery
4. Firebase Cloud Messaging - Push notifications

### 3.2 Functional Requirements

**ID**: REQ-FUNC-001
**Title**: User Authentication and Login Interface
**Statement**: The system shall provide a user interface for user login and authenticate user credentials against a defined user store.
**Rationale**: To secure the system and control access to features based on user identity, ensuring only authorized individuals can access system functionalities.
**Acceptance Criteria**:
*   The system shall display a login page containing fields for username/email and password, along with a submit button.
*   The system shall validate user-provided credentials via an integrated authentication API.
*   Upon successful authentication, the system shall grant the user access to authorized features and redirect them to the appropriate landing page.
*   Upon failed authentication (e.g., incorrect credentials), the system shall display an appropriate error message without disclosing specific authentication failures (e.g., "Invalid username or password").
*   The login user interface shall adhere to the provided mockups and detailed acceptance criteria.

**ID**: REQ-FUNC-002
**Title**: Code Line Change Calculation
**Statement**: The system shall calculate the number of added and deleted lines of code for each commit made to monitored code repositories.
**Rationale**: To provide metrics on individual and team code contributions, track developer activity, and inform contribution-based scoring.
**Acceptance Criteria**:
*   The system shall integrate with configured source code management (SCM) systems (e.g., Git-based repositories).
*   For each new commit processed from a monitored repository, the system shall identify the commit author.
*   For each new commit, the system shall accurately determine the count of lines added and lines deleted.
*   The system shall store the calculated lines added/deleted, the associated commit ID, the author's identifier, and the commit timestamp.

**ID**: REQ-FUNC-003
**Title**: Jira Task Completion Scoring
**Statement**: The system shall calculate and assign points to users based on the difficulty and 'Done' status of their assigned Jira tasks.
**Rationale**: To incentivize task completion and provide a quantifiable measure of contribution based on project management efforts.
**Acceptance Criteria**:
*   The system shall be configurable to map specific Jira task statuses (e.g., "Done", "Resolved") to a 'Completed' state.
*   The system shall retrieve task difficulty, such as Jira Story Points or a custom difficulty field, for relevant tasks.
*   When a Jira task assigned to a mapped user is updated to a 'Completed' status, the system shall calculate points based on its configured difficulty.
*   The system shall accumulate and persistently store the total points for each user based on their completed tasks.

**ID**: REQ-FUNC-004
**Title**: Jira Issue Status Change Event Listener
**Statement**: The system shall listen for and process real-time notifications whenever the status of an issue changes in the integrated Jira instance.
**Rationale**: To enable the system to react promptly to updates in project tasks, which is crucial for accurate scoring, progress tracking, and other data synchronization.
**Acceptance Criteria**:
*   The system shall establish and maintain a webhook subscription or an API polling mechanism to receive Jira issue update events.
*   Upon receiving an issue update event, the system shall parse the event data to identify the issue ID, the new status, the previous status, the assignee, and other relevant issue fields.
*   The system shall log or store a record of each processed issue status change event.

**ID**: REQ-FUNC-005
**Title**: Inactive Member Identification
**Statement**: The system shall identify and display a list of members who have not contributed code or completed tasks within a configurable period.
**Rationale**: To help team leaders identify and address potential disengagement or blockers within the team, facilitating proactive management.
**Acceptance Criteria**:
*   The system shall define "contribution" as either a code commit (tracked via REQ-FUNC-007) or a Jira task moved to a 'Done' status (tracked via REQ-FUNC-004).
*   The system shall maintain records of each user's latest contribution timestamp.
*   The system shall allow administrators to configure the inactivity threshold (e.g., default 7 days) via a dedicated setting.
*   Upon request, the system shall generate and display a list of users whose last contribution timestamp exceeds the configured inactivity threshold.
*   The displayed list shall include the user's name, their associated team/group, and the date of their last recorded contribution.

**ID**: REQ-FUNC-006
**Title**: External Account-to-System User Mapping
**Statement**: The system shall allow an administrator to map external account IDs (e.g., Jira Account IDs, Git User IDs) to internal system user accounts.
**Rationale**: To accurately attribute contributions and activities from external systems (like Jira and code repositories) to the correct users within the system, ensuring data integrity for scoring and reporting.
**Acceptance Criteria**:
*   The system shall provide an administrative interface accessible to users with appropriate roles (e.g., 'Admin') for managing user mappings.
*   An administrator shall be able to input or select an external account ID (e.g., Jira Account ID, Git Username) and link it to an existing internal system user account.
*   The system shall prevent mapping the same external account ID to multiple distinct internal user accounts.
*   The system shall allow a single internal user account to be mapped to multiple external account IDs (e.g., one Jira ID and one GitHub ID).
*   The system shall store these mappings persistently in a secure database.

**ID**: REQ-FUNC-007
**Title**: Code Repository Push Event Listener
**Statement**: The system shall listen for and record notifications whenever code is pushed to a monitored branch (e.g., main branch) in integrated code repositories.
**Rationale**: To provide real-time tracking of code contributions, enable the calculation of code-based metrics, and support features like inactivity detection.
**Acceptance Criteria**:
*   The system shall establish and maintain webhook subscriptions or API polling mechanisms to receive code push events from configured code repositories (e.g., GitHub, GitLab).
*   Upon receiving a code push event, the system shall extract details including the committer's identifier, repository name, target branch, commit IDs, and the timestamp of the push.
*   The system shall store a detailed record of each code push event, including all associated commit information.
*   The system shall filter incoming events to only process pushes to explicitly configured target branches (e.g., 'main', 'master', 'develop').

**ID**: REQ-FUNC-008
**Title**: Project Burndown Chart Display
**Statement**: The system shall display a burndown chart that visualizes the remaining work against time for a selected project or sprint.
**Rationale**: To provide users with a clear visual representation of project progress and help identify if the project is on track to meet its objectives.
**Acceptance Criteria**:
*   The system shall generate a burndown chart based on configured project data (e.g., Jira sprint data, estimated effort/story points).
*   The chart shall plot remaining work (Y-axis) against time (X-axis).
*   The chart shall include an ideal burndown line representing planned progress and an actual burndown line reflecting current progress.
*   The system shall allow users to select a specific project or sprint from a dropdown or similar control for which to display the chart.
*   The chart data shall be updated regularly (e.g., daily) to reflect the latest project status based on integrated systems.

**ID**: REQ-FUNC-009
**Title**: Group Contribution Report Export
**Statement**: The system shall allow authorized users (e.g., lecturers) to export a comprehensive report detailing the total scores and contributions of all members within a selected group or project.
**Rationale**: To provide lecturers and project managers with an aggregated view of team performance and individual contributions for evaluation, analysis, and record-keeping.
**Acceptance Criteria**:
*   The system shall provide a user interface option to initiate the export of a contribution report.
*   The report shall include, at minimum, each member's name, their total accumulated points from completed tasks, and their total lines of code added and deleted.
*   The system shall allow the user to select a specific group or project for which to generate the report.
*   The report shall be exportable in a common, machine-readable format such as CSV or Excel (XLSX).
*   Access to this export function shall be restricted to users with assigned roles such as 'Lecturer' or 'Admin'.
*   The report shall reflect the most current data available in the system at the time of export.

### 3.3 Quality of Service

#### 3.3.1 Performance

- Response time: < 2 seconds for 95% of API requests
- Support for 500 concurrent users
- Page load time: < 3 seconds on 3G connection
- Database queries: < 500ms for complex queries

#### 3.3.2 Security

- Authentication: JWT + OAuth 2.0
- Authorization: Role-Based Access Control (RBAC)
- Data encryption: HTTPS (TLS 1.3), passwords hashed with bcrypt
- Input validation: Protection against SQL Injection, XSS
- Session timeout: 30 minutes of inactivity

#### 3.3.3 Reliability

- Mean Time Between Failures (MTBF): > 720 hours
- Mean Time To Recovery (MTTR): < 1 hour
- Data backup: Automated every 6 hours, retained for 30 days
- No data loss on server restart

#### 3.3.4 Availability

- Uptime: 99.5% (allows ~3.6 hours downtime/month)
- Maintenance window: Sunday 2:00 - 4:00 AM
- Graceful degradation: Core features remain operational when external APIs fail

### 3.4 Compliance

_TBD — Define compliance requirements (standards, regulations, contracts)._

### 3.5 Design and Implementation

#### 3.5.1 Installation

_TBD_

#### 3.5.2 Build and Delivery

_TBD_

#### 3.5.3 Distribution

_TBD_

#### 3.5.4 Maintainability

_TBD_

#### 3.5.5 Reusability

_TBD_

#### 3.5.6 Portability

_TBD_

#### 3.5.7 Cost

_TBD_

#### 3.5.8 Deadline

_TBD_

#### 3.5.9 Proof of Concept

_TBD_

#### 3.5.10 Change Management

_TBD_

## 4. Verification

| Requirement ID | Verification Method | Test/Artifact Link | Status | Evidence |
|----------------|---------------------|--------------------|--------|----------|
|                |                     |                    |        |          |

## 5. Appendixes

_To be added as needed._
