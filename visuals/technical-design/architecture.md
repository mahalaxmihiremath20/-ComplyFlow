# ComplyFlow — Proposed System Architecture

## 1. System Overview

ComplyFlow is envisioned as a web-based platform that combines document processing, structured financial records, rule-based validation, and AI-assisted explanations.

The system is designed to take financial documents that are difficult to manually manage, extract useful information from them, and transform that information into organized records that can be checked and reviewed.

Instead of depending on one AI model for everything, ComplyFlow separates data extraction, validation, and explanation into different components. This helps make the proposed system easier to understand, maintain, and verify.

---

## 2. System Components

### A. Frontend — User Interface

The frontend is the part users directly interact with through their browser.

It is intended to provide:

- A document-upload interface
- A dashboard showing record summaries
- A list of flagged discrepancies
- Details explaining why an item needs attention
- A task list for pending reviews

**Proposed technology:** React + Tailwind CSS

### B. Backend — Application Server

The backend acts as the bridge between the user interface, document-processing modules, validation logic, AI services, and database.

It is responsible for:

- Receiving document uploads
- Managing processing requests
- Coordinating the different system modules
- Returning processed information to the frontend
- Managing user records and task updates

**Proposed technology:** Python + FastAPI

### C. Document Processing Module

This module aims to convert uploaded documents into information the system can work with.

The proposed process involves:

1. Reading the uploaded document.
2. Extracting text using OCR when the document is scanned.
3. Identifying relevant fields such as invoice number, date, supplier, taxable value, and tax amount.
4. Converting extracted information into a structured format.
5. Marking information that is unclear or needs manual verification.

### D. Validation Engine

The validation engine checks extracted records for conditions that may indicate errors or inconsistencies.

Examples of checks include:

- Missing required information
- Possible duplicate invoices
- Differences between matching records
- Invalid or inconsistent data formats
- Values requiring further verification

The engine is intended to use predefined rules for checks that can be explicitly defined, rather than relying entirely on AI-generated decisions.

### E. AI Assistance Module

The AI layer is intended to make system findings easier for users to understand.

It may help:

- Summarize detected issues
- Explain why a record has been flagged
- Generate understandable descriptions of discrepancies
- Suggest possible next steps for user review

AI is used for assistance and explanation, not as the sole authority for financial validation.

### F. Database

The database is intended to store:

- Document references
- Extracted information
- Structured invoice records
- Validation results
- Review statuses
- User action history

**Proposed technology:** SQLite during initial development, with the possibility of using Supabase if the project requires additional capabilities.

---

## 3. System Data Flow

The proposed system follows this sequence:

**Document Upload → Text & Data Extraction → Structured Records → Validation → Discrepancy Detection → AI Explanation → User Review**

Each component has a specific responsibility, allowing the system to process information in stages instead of treating a document as one unstructured input.

---

## 4. Why a Modular Architecture?

A modular architecture separates the system into smaller components, each responsible for a specific task.

This approach aims to:

- Make individual components easier to develop and test
- Allow document processing to be improved without redesigning the entire system
- Keep validation logic separate from AI-generated explanations
- Make future features easier to add
- Improve clarity when identifying the source of an error

---

## 5. Reliability & Human Review

Since the platform deals with financial records, an extracted value or AI-generated explanation should not automatically be treated as correct.

The proposed architecture includes a review stage where users can verify flagged findings against the original documents before deciding what action to take.

---

## Project Status

This architecture represents the proposed design of ComplyFlow. The components and data flow are documented for planning purposes and have not yet been implemented.
