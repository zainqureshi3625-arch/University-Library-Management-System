# Software Requirements Specification (SRS)

**University Library Management System** | Version 1.0 | 21 November 2026

**Team:** Zain Ul Abideen Qureshi (25MDSE019), Arbaz Khan (25MDSE007), Siam Ghani (25MDSE029)

**Programme:** BS Software Engineering, Centre of Artificial Intelligence (CAI), UET Mardan

**Repository:** https://github.com/zainqureshi3625-arch/University-Library-Management-System

---

## Revision History

| Version | Date | Description | Author |
|---|---|---|---|
| 0.1 | 19 Nov 2026 | Stakeholder analysis added | Arbaz Khan |
| 0.2 | 20 Nov 2026 | User stories and acceptance criteria added | Siam Ghani |
| 0.3 | 21 Nov 2026 | Requirements, assumptions, AI review and traceability matrix added | Team |
| 1.0 | 21 Nov 2026 | First complete SRS | Zain Ul Abideen Qureshi |

## Table of Contents

1. [Introduction](#1-introduction)
2. [Overall Description](#2-overall-description)
3. [Functional Requirements](#3-functional-requirements)
4. [Non-Functional Requirements](#4-non-functional-requirements)
5. [External Interface Requirements](#5-external-interface-requirements)
6. [Constraints, Assumptions and Dependencies](#6-constraints-assumptions-and-dependencies)
7. [Acceptance Criteria and Priorities](#7-acceptance-criteria-and-priorities)
8. [Traceability Matrix](#8-traceability-matrix)
9. [Appendix A: Summary of the AI Review](#9-appendix-a-summary-of-the-ai-review)

## 1. Introduction

### 1.1 Purpose

This document says what the University Library Management System (LMS) must do. It is written for the teacher, the team and anyone who will design or test the system later. It uses IEEE and ISO ideas for writing requirements only as a guide. It does not claim formal compliance with any standard.

### 1.2 Scope

A university library keeps records of books, borrowing, returns, students and overdue books by hand or with an old system. The LMS will manage:

- Books and book copies
- Library members (students and faculty members)
- Borrowing and returning books
- Reservations
- Reminders and overdue notices

The team works like a software engineering team. It studies the problem, writes the requirements, draws diagrams and designs a prototype. It does not build the full working system.

**Not included:** online payment, barcode scanning, mobile apps, fines, loan renewal, and reports for the administrator. These can be added later if the library needs them.

### 1.3 Definitions

| Word | Meaning |
|---|---|
| LMS | Library Management System, the system described in this document |
| SRS | Software Requirements Specification, this document |
| Stakeholder | A person or group who uses the system or is affected by it |
| Member | A registered library user (a student or a faculty member) |
| User | Anyone who logs in to the system (member, librarian or administrator) |
| Librarian | A staff member who manages books, members, issues and returns |
| Book copy | One physical copy of a book. A book can have many copies |
| Overdue | A borrowed book that is not returned by its due date |
| Reservation | A request to get a book that is already borrowed |
| FR / NFR | Functional requirement (what the system does) / Non-functional requirement (how well it works) |
| User story | A short sentence: As a ..., I want ..., so that ... |
| Acceptance criteria | Clear checks that show a requirement or story works |

### 1.4 References

These files are in the `requirements` folder of the repository:

- `stakeholder-analysis.md`
- `requirements-list.md`
- `user-stories.md`
- `assumptions-and-constraints.md`
- `ai-review.md`
- `traceability-matrix.md`

## 2. Overall Description

### 2.1 Product Perspective

The LMS is a new system that replaces manual records or an outdated system. We expect it to run on a server and to be used in a web browser on a computer or a phone.

### 2.2 Product Functions

- Keep records of books and book copies, and search them
- Register members and keep their records
- Issue books, record returns and set due dates
- Reserve books that are borrowed
- Show members their borrowed books, and send reminders and overdue notices
- Show the librarian the list of overdue books
- Let users log in and see only the tasks of their role

### 2.3 Stakeholders and User Characteristics

| Stakeholder | Role in the library | Importance | Needs (from the stakeholder analysis) |
|---|---|---|---|
| Student | Searches for, borrows and returns books | High | SN-01 to SN-04 |
| Librarian | Manages books, members, borrowing and returns | High | SN-05 to SN-08 |
| Faculty Member | Borrows books for teaching and research | Medium | SN-09 to SN-11 |
| Library Administrator | Controls library rules, accounts and reports | High | SN-12 to SN-14 |
| University Management | Decides about library budget and services | Low | SN-15 |
| IT Support Staff | Installs, backs up and looks after the system | Medium | SN-16, SN-17 |

Students and faculty members use the system from time to time and need a simple screen. Librarians use it every day and get training.

### 2.4 Operating Environment

The system is used through a web browser on a computer or a phone, with the university network or internet. It stores its data in a database on a server.

## 3. Functional Requirements

| ID | Name | Requirement | Source need | Priority |
|---|---|---|---|---|
| FR-01 | Book records | The system must let a librarian add, update and remove book records (title, author, ISBN and category) and keep a record of each copy of a book with its status (available, borrowed or reserved). The system must not accept a second book with an ISBN that already exists. | SN-05 | High |
| FR-02 | Search | The system must let users search for books by title, author or category, and must show if the book is available. A search with part of a word must work, and capital and small letters are treated the same. | SN-01, SN-09 | High |
| FR-03 | Members | The system must let a librarian register members (student or faculty) and keep their records. | SN-12 | High |
| FR-04 | Issue a book | The system must let a librarian issue a book to a member. The due date is set from the library loan period. | SN-06 | High |
| FR-05 | Return a book | The system must let a librarian record the return of a book, and the copy becomes available again. | SN-06 | High |
| FR-06 | Reservations | The system must let a member reserve a book that is already borrowed, and must serve the reservations in order (first come, first served). | SN-02, SN-08, SN-10 | Medium |
| FR-07 | My books | The system must let a member see his or her borrowed books and their due dates. | SN-03 | Medium |
| FR-08 | Reminders and notices | The system must send a reminder to a member 2 days before the due date, and an overdue notice on the day a borrowed book becomes overdue. | SN-04, SN-07, SN-11 | Medium |
| FR-09 | Overdue list | The system must find overdue books and show the list to the librarian. | SN-07 | High |
| FR-10 | Login and roles | The system must ask users to log in and must allow each user only the tasks of his or her role. | SN-14 | High |

## 4. Non-Functional Requirements

| ID | Name | Requirement | How we check it | Source need | Priority |
|---|---|---|---|---|---|
| NFR-01 | Speed | Search results must appear within 3 seconds in normal use. | Run 20 searches. Every result page appears in 3 seconds or less. | SN-01 | High |
| NFR-02 | Easy to use | A new librarian must be able to issue and return books without help after one hour of training. | A new librarian gets 1 hour of training, then issues and returns 5 books without help. | SN-06 | Medium |
| NFR-03 | Security | Passwords must be stored in a protected (encrypted) form, and only logged-in users may see member data. | Check that passwords cannot be read in the stored data, and that a student cannot open librarian pages. | SN-14, SN-17 | High |
| NFR-04 | Availability | The system must be working at least 99% of the time during library opening hours. | Measure the working time during opening hours every month. It is at least 99%. | SN-16 | Medium |

## 5. External Interface Requirements

| Interface | Description |
|---|---|
| User interface | Web pages for: login, student dashboard, book search and results, book details and reservation, and the librarian dashboard for issuing and returning books. The pages must be simple and look the same everywhere. The screens will be designed as a clickable prototype later in the project. |
| Hardware | A server for the system, and a computer or a phone for each user. No special hardware is needed (barcode scanners are not required). |
| Software | A web browser for users. A database for books, members, loans and reservations. An email or message service to send reminders and overdue notices (FR-08). |
| Communication | Users reach the system over the university network or the internet. Reminders and overdue notices are sent by email or shown on the screen. |

## 6. Constraints, Assumptions and Dependencies

### 6.1 Assumptions and Constraints

| ID | Type | Statement | Why it matters |
|---|---|---|---|
| A-01 | Assumption | Library staff will give correct information about books, book copies and members. | If the data is wrong, the records and reports will also be wrong. |
| A-02 | Assumption | Users have a computer or a phone with a web browser, and the university network or internet. | If not, users cannot reach the system. |
| A-03 | Assumption | The library gives the team its rules (loan period and number of books for each member) and its opening hours. | FR-04 needs the loan period, and NFR-04 needs the opening hours. |
| C-01 | Constraint | The team has three members and limited time, and must follow the deadlines given by the teacher. | The work must be planned and shared carefully. |
| C-02 | Constraint | Git and GitHub must be used, and the team does not build the full working system. | All documents are kept in the shared repository. No code is needed. |

### 6.2 Dependencies

- The library staff must give the book and member data, the library rules and the opening hours (A-01, A-03).
- An email or message service is needed to send reminders and overdue notices (FR-08).
- The requirements depend on the stakeholder needs in `stakeholder-analysis.md`.

## 7. Acceptance Criteria and Priorities

### 7.1 Priorities

High means very important and Medium means important.

| Priority | Functional requirements | Non-functional requirements |
|---|---|---|
| High | FR-01, FR-02, FR-03, FR-04, FR-05, FR-09, FR-10 | NFR-01, NFR-03 |
| Medium | FR-06, FR-07, FR-08 | NFR-02, NFR-04 |

### 7.2 Acceptance Criteria of the User Stories

| ID | User story | Requirements | Acceptance criteria |
|---|---|---|---|
| US-01 | As a student, I want to search for a book by title, author or category, so that I can find it quickly. | FR-02, NFR-01 | AC1: Search works with a title, an author or a category, and with part of a word. AC2: Results appear within 3 seconds. AC3: Each result shows the title, the author and if the book is available. AC4: If no book is found, the system shows the message 'No book found'. |
| US-02 | As a student, I want to reserve a book that is already borrowed, so that I get it when it is returned. | FR-06 | AC1: The Reserve button appears only when no copy is available. AC2: The system shows a confirmation message after the reservation. AC3: I cannot reserve the same book twice. AC4: When the book is returned, the first member in the reservation list gets it. |
| US-03 | As a student, I want to see my borrowed books and get a reminder before the due date, so that I can return them on time. | FR-07, FR-08 | AC1: The list shows the title, the issue date and the due date of each of my books. AC2: The list shows only my own books. AC3: A reminder is sent 2 days before the due date and shows the book title and the due date. AC4: No reminder is sent for a book that is already returned. |
| US-04 | As a librarian, I want to add, update and remove book records, so that the library catalogue stays correct. | FR-01 | AC1: I can save a book with title, author, ISBN and category. AC2: A new book appears in the search within 1 minute. AC3: The system rejects a book with an ISBN that already exists and shows a message. AC4: A book that has a borrowed copy cannot be removed. |
| US-05 | As a librarian, I want to issue a book to a registered member, so that the borrowing is recorded. | FR-03, FR-04 | AC1: I can only issue a book to a member who is registered. AC2: The system sets the due date from the library loan period. AC3: The book status changes to Borrowed. AC4: Issuing a book takes less than 1 minute. |
| US-06 | As a librarian, I want to record the return of a book, so that the book becomes available again. | FR-05, FR-06 | AC1: The book status changes to Available after the return. AC2: If another member has a reservation, the status changes to Reserved for that member. AC3: A late return is marked as late. |
| US-07 | As a librarian, I want to see a list of overdue books, so that I can ask members to return them. | FR-08, FR-09 | AC1: The list shows the member, the book, the due date and the number of days late. AC2: The list is sorted with the most late book first. AC3: An overdue notice is sent to the member on the day the book becomes overdue. |
| US-08 | As a user (any role), I want to log in to the system and see only my own tasks, so that the library data stays safe. | FR-10, NFR-03 | AC1: A wrong password shows an error message and does not log in the user. AC2: After 5 wrong tries the account is locked for 10 minutes. AC3: A student cannot open librarian pages. AC4: Passwords are never shown on the screen. |

The checks for NFR-02 and NFR-04 are in the table of non-functional requirements (section 4).

## 8. Traceability Matrix

This table connects each requirement to the stakeholder need it comes from, the user story that covers it, and the acceptance criteria or check that tests it.

| Requirement | Name | Priority | Stakeholder need | User story | Acceptance criteria or check | Status |
|---|---|---|---|---|---|---|
| FR-01 | Book records | High | SN-05 | US-04 | US-04: AC1 to AC4 | Covered |
| FR-02 | Search | High | SN-01, SN-09 | US-01 | US-01: AC1 to AC4 | Covered |
| FR-03 | Members | High | SN-12 | US-05 | US-05: AC1 to AC4 | Covered |
| FR-04 | Issue a book | High | SN-06 | US-05 | US-05: AC1 to AC4 | Covered |
| FR-05 | Return a book | High | SN-06 | US-06 | US-06: AC1 to AC3 | Covered |
| FR-06 | Reservations | Medium | SN-02, SN-08, SN-10 | US-02, US-06 | US-02: AC1 to AC4, US-06: AC1 to AC3 | Covered |
| FR-07 | My books | Medium | SN-03 | US-03 | US-03: AC1 to AC4 | Covered |
| FR-08 | Reminders and notices | Medium | SN-04, SN-07, SN-11 | US-03, US-07 | US-03: AC1 to AC4, US-07: AC1 to AC3 | Covered |
| FR-09 | Overdue list | High | SN-07 | US-07 | US-07: AC1 to AC3 | Covered |
| FR-10 | Login and roles | High | SN-14 | US-08 | US-08: AC1 to AC4 | Covered |
| NFR-01 | Speed | High | SN-01 | US-01 | US-01: AC1 to AC4 | Covered |
| NFR-02 | Easy to use | Medium | SN-06 | - | Check in section 4 | Covered |
| NFR-03 | Security | High | SN-14, SN-17 | US-08 | US-08: AC1 to AC4 | Covered |
| NFR-04 | Availability | Medium | SN-16 | - | Check in section 4 | Covered |

All 14 requirements are covered.

## 9. Appendix A: Summary of the AI Review

The requirements were given to an AI assistant (Claude) to check for unclear words, missing items, clashes and points that cannot be tested. The team decided on each suggestion. The accepted changes are already written into this SRS. The full table is in `ai-review.md`.

| No. | Requirement | Problem | Decision |
|---|---|---|---|
| 1 | FR-02 | Unclear: search with part of a word | Accepted |
| 2 | NFR-02 | Unclear: 'without help' is not exact | Accepted |
| 3 | NFR-04 | Cannot test: opening hours not written | Accepted |
| 4 | FR-08 | Unclear: no time for reminder and notice | Accepted |
| 5 | FR-04 | Missing: how the due date is decided | Accepted |
| 6 | Whole list | Missing: loan renewal | Rejected (not in the case) |
| 7 | Whole list | Missing: fines for late books | Rejected (outside the project) |
