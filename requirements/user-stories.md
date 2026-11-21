# User Stories and Acceptance Criteria

University Library Management System

## 1. How to Read This Document

- **User story:** one short sentence about what a user wants: *As a ..., I want ..., so that ...*
- **Acceptance criteria:** clear checks that show the story works. Each check has a number or a clear result.
- **Related requirements:** the requirements (from `requirements-list.md`) that the story covers.

## 2. Summary

| ID | Role | I want to | Related requirements | Priority |
|:---:|---|---|:---:|:---:|
| US-01 | Student | search for a book by title, author or category | FR-02, NFR-01 | High |
| US-02 | Student | reserve a book that is already borrowed | FR-06 | Medium |
| US-03 | Student | see my borrowed books and get a reminder before the due date | FR-07, FR-08 | Medium |
| US-04 | Librarian | add, update and remove book records | FR-01 | High |
| US-05 | Librarian | issue a book to a registered member | FR-03, FR-04 | High |
| US-06 | Librarian | record the return of a book | FR-05, FR-06 | High |
| US-07 | Librarian | see a list of overdue books | FR-08, FR-09 | High |
| US-08 | User (any role) | log in to the system and see only my own tasks | FR-10, NFR-03 | High |

## 3. User Stories in Detail

### US-01

**Story:** As a student, I want to search for a book by title, author or category, so that I can find it quickly.

**Related requirements:** FR-02, NFR-01  |  **Priority:** High

**Acceptance criteria:**

1. Search works with a title, an author or a category, and with part of a word.
2. Results appear within 3 seconds.
3. Each result shows the title, the author and if the book is available.
4. If no book is found, the system shows the message "No book found".

### US-02

**Story:** As a student, I want to reserve a book that is already borrowed, so that I get it when it is returned.

**Related requirements:** FR-06  |  **Priority:** Medium

**Acceptance criteria:**

1. The Reserve button appears only when no copy is available.
2. The system shows a confirmation message after the reservation.
3. I cannot reserve the same book twice.
4. When the book is returned, the first member in the reservation list gets it.

### US-03

**Story:** As a student, I want to see my borrowed books and get a reminder before the due date, so that I can return them on time.

**Related requirements:** FR-07, FR-08  |  **Priority:** Medium

**Acceptance criteria:**

1. The list shows the title, the issue date and the due date of each of my books.
2. The list shows only my own books.
3. A reminder is sent 2 days before the due date and shows the book title and the due date.
4. No reminder is sent for a book that is already returned.

### US-04

**Story:** As a librarian, I want to add, update and remove book records, so that the library catalogue stays correct.

**Related requirements:** FR-01  |  **Priority:** High

**Acceptance criteria:**

1. I can save a book with title, author, ISBN and category.
2. A new book appears in the search within 1 minute.
3. The system rejects a book with an ISBN that already exists and shows a message.
4. A book that has a borrowed copy cannot be removed.

### US-05

**Story:** As a librarian, I want to issue a book to a registered member, so that the borrowing is recorded.

**Related requirements:** FR-03, FR-04  |  **Priority:** High

**Acceptance criteria:**

1. I can only issue a book to a member who is registered.
2. The system sets the due date from the library loan period.
3. The book status changes to Borrowed.
4. Issuing a book takes less than 1 minute.

### US-06

**Story:** As a librarian, I want to record the return of a book, so that the book becomes available again.

**Related requirements:** FR-05, FR-06  |  **Priority:** High

**Acceptance criteria:**

1. The book status changes to Available after the return.
2. If another member has a reservation, the status changes to Reserved for that member.
3. A late return is marked as late.

### US-07

**Story:** As a librarian, I want to see a list of overdue books, so that I can ask members to return them.

**Related requirements:** FR-08, FR-09  |  **Priority:** High

**Acceptance criteria:**

1. The list shows the member, the book, the due date and the number of days late.
2. The list is sorted with the most late book first.
3. An overdue notice is sent to the member on the day the book becomes overdue.

### US-08

**Story:** As an user (any role), I want to log in to the system and see only my own tasks, so that the library data stays safe.

**Related requirements:** FR-10, NFR-03  |  **Priority:** High

**Acceptance criteria:**

1. A wrong password shows an error message and does not log in the user.
2. After 5 wrong tries the account is locked for 10 minutes.
3. A student cannot open librarian pages.
4. Passwords are never shown on the screen.

## 4. Notes

- There are 8 user stories. The checks for NFR-02 and NFR-04 are in the table of non-functional requirements in `requirements-list.md`.
- The user story numbers (US-01, US-02 and so on) are used in the traceability matrix.
