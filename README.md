# NyayaSetu

### A Relational Database System for Judiciary Information Management

NyayaSetu (न्यायसेतु — "Bridge to Justice") is a relational database management system designed to model, organize, and manage the end-to-end workflow of the Indian judicial system. It provides a centralized, normalized platform for storing and retrieving information related to courts, judges, lawyers, litigants, cases, hearings, legal documents, and judgments — replacing the fragmented, paper-heavy record-keeping practices that currently slow down judicial administration.

The project follows a complete database engineering lifecycle: conceptual modeling with an Entity–Relationship Diagram (ERD), translation into a relational schema, normalization up to Boyce–Codd Normal Form (BCNF), and implementation using SQL DDL and queries.

---

## Table of Contents

- [Problem Statement](#-problem-statement)
- [Objectives](#-objectives)
- [System Overview](#-system-overview)
- [User Categories](#-user-categories)
- [Core Functionalities](#-core-functionalities)
- [Database Design Process](#-database-design-process)
- [Repository Structure](#-repository-structure)
- [Technologies Used](#-technologies-used)
- [Documentation](#-documentation)
- [Sample Database Operations](#-sample-database-operations)
- [Getting Started](#-getting-started)
- [Team](#-team)
- [License](#-license)

---

## Problem Statement

The Indian judicial system handles millions of active cases spread across courts of varying jurisdictions. Records related to cases, hearings, lawyers, litigants, and evidence are frequently scattered across disconnected systems or maintained as physical files. This fragmentation makes it difficult to track case progress, retrieve information quickly, and manage proceedings efficiently — leaving judges, lawyers, and litigants struggling to access timely and accurate case data.

NyayaSetu addresses this problem by designing a single, structured, and normalized relational database that centralizes judicial information, improves transparency, and supports efficient day-to-day operations of judicial institutions.

---

## Objectives

- Design a comprehensive relational database for judicial information management.
- Model the relationships between courts, judges, lawyers, litigants, cases, and hearings.
- Provide a centralized repository for legal documents and judicial records.
- Support efficient querying and retrieval of judicial information through SQL.
- Maintain data consistency and eliminate redundancy through normalization to BCNF.
- Prevent insertion, deletion, and update anomalies across the schema.
- Demonstrate the complete database design lifecycle — from conceptual modeling to SQL implementation.

---

## System Overview

NyayaSetu manages the complete lifecycle of a judicial proceeding. Every case entered into the system is linked to its court, assigned judge, representing lawyers, petitioners, and respondents, along with its hearing schedule and supporting legal documents. As proceedings progress, case status, hearing outcomes, judgments, and court orders are updated in real time — while the complete historical record of the case is preserved.

The system is designed to serve multiple categories of users, enabling both open public access to non-confidential information and secure administrative management of judicial proceedings.

---

## User Categories

### General Public (Unregistered Users)
Can access non-confidential judicial information without authentication:
- Search cases using parameters such as Case Number, Case Name, Category, Court, Judge, Lawyer, Filing Date, or Petitioner/Respondent Name.
- View case summaries, status, and category.
- View hearing schedules and published judgments/orders.

### Judiciary Bodies (Judges & Court Officials)
Authorized officials responsible for maintaining the integrity of the database:
- Register new cases and maintain records through the case lifecycle.
- Schedule hearings and record hearing outcomes.
- Upload legal documents such as petitions, evidence, and court orders.
- Update case status and record judgments.
- Generate administrative and court activity reports.

### Lawyers / Advocates
Registered advocates with access to their assigned cases:
- Monitor case progress and review hearing schedules.
- Access legal documents relevant to their proceedings.

### Litigants (Petitioners & Respondents)
Parties to a case with secure access to their own case data:
- Track hearing schedules and case status.
- Review documents associated with ongoing proceedings.

---

## Core Functionalities

| Module | Description |
|---|---|
| Court Management | Maintain records of courts and jurisdictions |
| Judge Management | Maintain judge profiles and case assignments |
| Lawyer Management | Registration and case association for advocates |
| Litigant Registration | Records for petitioners and respondents |
| Case Registration | Formal entry and tracking of new cases |
| Case Status Tracking | Real-time updates through the case lifecycle |
| Hearing Scheduling | Scheduling and outcome recording for hearings |
| Judgment Management | Recording and publishing case judgments |
| Legal Document Repository | Centralized storage for petitions, evidence, and orders |
| Public Case Search | Multi-parameter search for non-confidential cases |
| Administrative Reporting | Court-wise, monthly, and annual judicial summaries |

---

## Database Design Process

**1. Entity–Relationship Modeling** — Identifies all major entities in judicial proceedings (courts, judges, lawyers, litigants, cases, hearings, documents) and defines the relationships and cardinality constraints between them.

**2. Relational Schema Design** — Translates the ER model into a relational schema that accurately represents all entities, attributes, and relationships.

**3. Normalization (up to BCNF)** — The relational schema is normalized to Boyce–Codd Normal Form to eliminate redundancy and prevent insertion, deletion, and update anomalies, ensuring long-term data integrity.

**4. SQL Implementation** — The normalized schema is implemented using SQL DDL statements, along with a set of queries demonstrating retrieval, reporting, and administrative operations.

---

## Repository Structure

```
NyayaSetu/
│
├── README.md
├── LICENSE
│
├── sql/
│   ├── ddl.sql                     # Database & table creation scripts
│   └── judiciary_queries.pdf       # Sample SQL queries and reports
│
├── erd/
│   ├── entity_relationship_diagram.png
│   └── relational_schema.png
│
├── bcnf-proof/
│   └── normalization_proof.pdf     # Complete BCNF normalization proof
│
├── screenshots/
│   └── ...                         # Application/query output screenshots
│
└── docs/
    └── project_report.pdf          # Full project documentation
```

---

## Technologies Used

- **MySQL** — Relational database engine
- **SQL** — Schema definition and query implementation
- **ER Modeling** — Conceptual database design
- **Database Normalization (BCNF)** — Schema refinement and integrity

---

## Documentation

| Document | Description |
|---|---|
| Entity–Relationship Diagram | Conceptual design of the database |
| Relational Schema | Logical database design derived from the ER model |
| BCNF Proof | Step-by-step normalization to Boyce–Codd Normal Form |
| `ddl.sql` | SQL scripts for database and table creation |
| Judiciary Queries | Sample SQL queries and generated reports |

---

## Sample Database Operations

- Search cases using multiple criteria (case number, category, court, judge, etc.)
- Retrieve all cases assigned to a specific judge
- Monitor upcoming and past hearing schedules
- View pending and closed cases
- Access the complete history of a case
- Manage and retrieve legal documents linked to a case
- Generate court-wise and judge-wise activity reports
- Produce monthly and annual judicial summaries

---

## Getting Started

1. Clone the repository:
   ```bash
   git clone https://github.com/<your-username>/NyayaSetu.git
   cd NyayaSetu
   ```
2. Set up a MySQL instance and create a new database:
   ```sql
   CREATE DATABASE nyayasetu;
   ```
3. Run the DDL script to create the schema:
   ```bash
   mysql -u <username> -p nyayasetu < sql/ddl.sql
   ```
4. Explore the sample queries in `sql/judiciary_queries.pdf` to test the database.

---

## Team

This project was developed as part of a Database Management Systems course.

| Name | Student ID |
|---|---|
| Marm Bhatt | 202401408 |
| Niranjan Panchal | 202401441 |
| Rushabh Shah | 202401463 |
| Siddh Shah | 202401473 |
| Vedant Shah | 202401475 |

---

## License

This project was developed solely for **academic and educational purposes** as part of a Database Management Systems course. See [`LICENSE`](./LICENSE) for details.

---

<p align="center">Built with a commitment to making judicial information more accessible, transparent, and efficient.</p>
