# Software Requirements Specifications

##  SkillSnap Showcase Portfolio – Swipe-based Personal Branding Platform

| Field | Value |
|-------|-------|
| **Project** |  SkillSnap Showcase Portfolio – Swipe-based Personal Branding Platform |
| **Group** | GSP26SE06 |
| **Authors** | Danheng, Pham Team Leader, Student Nguyen |
| **Supervisors** | Le Van Supervisor |
| **Date** | 2026-04-10 |

---

## 1. Introduction

### 1.1 Purpose

This document describes the complete software requirements for the Student Management System (SMS). It is intended for the development team, project supervisors, and all relevant stakeholders.

### 1.2 Scope

The Student Management System is a web application that manages student information, grades, schedules, and notifications. Goal: Digitize management processes, reducing manual processing time by 80%. Out of scope: Financial management, facility management.

> **Topic Description**: a)	Context:
 The hospitality industry requires seamless coordination, exceptional service quality, and well-structured digital systems to support daily operations. As hotel chains grow and manage multiple branches, the need for a modern, centralized management platform becomes increasingly important. Traditional methods often lead to fragmented workflows, inconsistent data, and reduced operational efficiency.
This project aims to develop an elegant, intuitive, and fully integrated hotel chain management website designed to support both staff operations and customer interactions. The system focuses on creating a smooth digital experience that reflects professionalism, convenience, and a high standard of service.
The platform provides core functions such as centralized room and reservation management, customer information tracking, service coordination across branches, staff scheduling, and financial monitoring. With a clean and modern interface, the system enhances productivity for hotel staff while offering customers a pleasant and effortless online experience.
By combining practical management tools with refined design principles, the project delivers a unified solution that supports efficient hotel chain operations and elevates overall service quality.
b)	Proposed Solutions 
Develop a web and mobile platform for car owners, customers, staff, and admins. Enhance the system to improve user experience, fraud prevention, and operational efficiency:
- Car Owner: Manage cars, bookings, customers, payments.
- Customer: Search, book, review, pay for self-driving cars.
- Staff: Support users, manage feedback, reports.
- Admin: Oversee policies, compliance, revenue, fraud detection.
c)	Functional requirement 
The main processing flows are as follows:
✔	Car Owners:
1)	Register and list self-drive cars for rent
2)	Manage car availability, pricing, and booking calendar
3)	Receive and respond to customer inquiries
4)	Track car usage and maintenance schedules
5)	Manage payments 

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

1. **Authentication Modules Deployment**
2. **gggggggggg** — gggggggggg
3. **Authentication Modules Deployment**
4. **hi**
5. **tesr3** — 1111
6. **Test AI Summarize Task**
7. **Authentication Modules Deployment**
8. **Authentication Module Deployment**
9. **Setup Sprint Management Module**
10. **Setup Sprint Management Module**
11. **Setup Sprint Management Module**
12. **epic draft**

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

- **ID**: REQ-FUNC-001
- **Title**: Create Login User Interface
- **Statement**: _To be defined_
- **Rationale**: _To be defined_
- **Acceptance Criteria**: _To be defined_

- **ID**: REQ-FUNC-002
- **Title**: Override
- **Statement**: adc
- **Rationale**: _To be defined_
- **Acceptance Criteria**: _To be defined_

- **ID**: REQ-FUNC-003
- **Title**: Integrate Login API
- **Statement**: _To be defined_
- **Rationale**: _To be defined_
- **Acceptance Criteria**: _To be defined_

- **ID**: REQ-FUNC-004
- **Title**: Create Login User Interface
- **Statement**: _To be defined_
- **Rationale**: _To be defined_
- **Acceptance Criteria**: _To be defined_

- **ID**: REQ-FUNC-005
- **Title**: As an Academic Admin
- **Statement**: _To be defined_
- **Rationale**: _To be defined_
- **Acceptance Criteria**: _To be defined_

- **ID**: REQ-FUNC-006
- **Title**: Integrate Login API
- **Statement**: _To be defined_
- **Rationale**: _To be defined_
- **Acceptance Criteria**: _To be defined_

- **ID**: REQ-FUNC-007
- **Title**: Create Login User Interface
- **Statement**: _To be defined_
- **Rationale**: _To be defined_
- **Acceptance Criteria**: _To be defined_

- **ID**: REQ-FUNC-008
- **Title**: Ka
- **Statement**: ka
- **Rationale**: _To be defined_
- **Acceptance Criteria**: _To be defined_

- **ID**: REQ-FUNC-009
- **Title**: Integrate Login API
- **Statement**: _To be defined_
- **Rationale**: _To be defined_
- **Acceptance Criteria**: _To be defined_

- **ID**: REQ-FUNC-010
- **Title**: Integrate Login API
- **Statement**: _To be defined_
- **Rationale**: _To be defined_
- **Acceptance Criteria**: _To be defined_

- **ID**: REQ-FUNC-011
- **Title**: Create Login User Interface
- **Statement**: _To be defined_
- **Rationale**: _To be defined_
- **Acceptance Criteria**: _To be defined_

- **ID**: REQ-FUNC-012
- **Title**: test1
- **Statement**: _To be defined_
- **Rationale**: _To be defined_
- **Acceptance Criteria**: _To be defined_

- **ID**: REQ-FUNC-013
- **Title**: Kin
- **Statement**: 
- **Rationale**: _To be defined_
- **Acceptance Criteria**: _To be defined_

- **ID**: REQ-FUNC-014
- **Title**: Test product
- **Statement**: 
- **Rationale**: _To be defined_
- **Acceptance Criteria**: _To be defined_



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
