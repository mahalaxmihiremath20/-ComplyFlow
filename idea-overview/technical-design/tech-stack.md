# ComplyFlow — Proposed Technology Stack

## 1. Overview

ComplyFlow is planned as a web-based application with a frontend for user interaction, a backend for processing requests, document-processing tools for extracting financial information, a validation engine for checking records, and an AI layer for generating understandable explanations.

The technology choices are based on keeping the initial system practical to develop, modular, and suitable for a future prototype.

---

## 2. Frontend

### React
React is proposed for building the user interface of ComplyFlow.

It allows the dashboard to be divided into reusable components, such as document-upload panels, record tables, alert cards, and review sections.

**Why React?**
- Supports reusable UI components.
- Makes interactive dashboards easier to organize.
- Has a large ecosystem of libraries and learning resources.

### Tailwind CSS
Tailwind CSS is proposed for styling the frontend.

It allows developers to apply layout, spacing, colors, and responsive design directly through utility classes, helping build a consistent interface.

---

## 3. Backend

### Python
Python is proposed as the primary backend programming language.

It is widely used for data processing, automation, AI integrations, and document-analysis workflows, making it a practical choice for the core processing modules.

### FastAPI
FastAPI is proposed as the backend framework.

It will help expose application functionality through API endpoints, allowing the React frontend to communicate with document processing, validation, and data-storage modules.

**Example responsibility:** Receive an uploaded document from the frontend and coordinate its processing.

---

## 4. Document Processing

### OCR — Optical Character Recognition

OCR technology is proposed for reading text from scanned documents or image-based invoices.

It helps convert document images into machine-readable text, which can then be processed to identify relevant information.

OCR is not assumed to be perfectly accurate. Extracted information may require verification, especially when document quality is poor.

---

## 5. Validation & Data Processing

### Python-Based Validation Rules

Python will be used to implement defined checks against structured records.

Examples include:

- Checking for missing information
- Identifying possible duplicate records
- Comparing corresponding values
- Validating formats and data consistency

Rule-based checks are preferred wherever the expected condition can be clearly defined, helping make findings easier to trace and verify.

---

## 6. AI Integration

### Large Language Model (LLM) API

An LLM API is proposed to assist with explaining detected issues in simple language, summarizing records, and generating review guidance.

The AI layer is intended to work with the results of the validation engine rather than independently deciding whether financial records are correct.

AI-generated explanations will require verification and will not be treated as authoritative tax advice.

---

## 7. Database

### SQLite — Initial Development

SQLite is proposed for early development because it is lightweight and can store structured information without requiring a separate database server.

It may be suitable for testing the initial workflow and storing sample records.

### Supabase — Possible Future Option

Supabase may be considered if ComplyFlow requires hosted storage, multi-user access, authentication, or additional backend capabilities.

It is a possible future option rather than a finalized requirement.

---

## 8. Version Control & Collaboration

### Git
Git is used to track changes in source files and documentation over time, allowing developers to maintain project history and collaborate.

### GitHub
GitHub hosts the repository and provides a shared workspace for project documentation, code, issue tracking, and collaboration.

---

## 9. Technology Summary

| Layer | Technology | Planned Responsibility |
|---|---|---|
| Frontend | React | User interface and dashboard |
| Styling | Tailwind CSS | Layout and visual design |
| Backend Language | Python | Processing and application logic |
| Backend Framework | FastAPI | APIs and communication |
| Document Processing | OCR | Text extraction |
| Validation | Python rules | Record checks and comparisons |
| AI Layer | LLM API | Explanations and summaries |
| Database | SQLite | Initial structured storage |
| Future Database Option | Supabase | Potential hosted backend |
| Version Control | Git + GitHub | Change tracking and collaboration |

---

## Project Status

These technologies represent the proposed stack. Technology integration, testing, and final selection will take place during implementation.
