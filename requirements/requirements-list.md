# Requirements List

University Library Management System

## 1. How to Read This Document

- **Functional requirement (FR):** what the system does.
- **Non-functional requirement (NFR):** how well the system works (speed, safety, ease of use).
- **Source need:** the stakeholder need (from `stakeholder-analysis.md`) that this requirement comes from.
- **Priority:** High means very important, Medium means important.

## 2. Functional Requirements

| ID | Name | Requirement | Source need | Priority |
|:---:|---|---|:---:|:---:|
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

## 3. Non-Functional Requirements

| ID | Name | Requirement | How we check it | Source need | Priority |
|:---:|---|---|---|:---:|:---:|
| NFR-01 | Speed | Search results must appear within 3 seconds in normal use. | Run 20 searches. Every result page appears in 3 seconds or less. | SN-01 | High |
| NFR-02 | Easy to use | A new librarian must be able to issue and return books without help after one hour of training. | A new librarian gets 1 hour of training, then issues and returns 5 books without help. | SN-06 | Medium |
| NFR-03 | Security | Passwords must be stored in a protected (encrypted) form, and only logged-in users may see member data. | Check that passwords cannot be read in the stored data, and that a student cannot open librarian pages. | SN-14, SN-17 | High |
| NFR-04 | Availability | The system must be working at least 99% of the time during library opening hours. | Measure the working time during opening hours every month. It is at least 99%. | SN-16 | Medium |

## 4. Summary

| Type | Number |
|---|---:|
| Functional requirements | 10 |
| Non-functional requirements | 4 |
| **Total** | **14** |

## 5. Notes

- Every requirement has a number (FR-01, NFR-01 and so on). The numbers are used in the user stories, the traceability matrix and the SRS.
- Every requirement comes from at least one stakeholder need.
- This list already includes the changes accepted in the AI review (see `ai-review.md`).
