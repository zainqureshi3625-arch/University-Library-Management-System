# AI Review of the Requirements

University Library Management System

## 1. What is This?

We gave our requirements to an AI assistant (Claude) and asked: *What is wrong or missing?* This page shows its suggestions, and what the team decided.

## 2. The Kinds of Problems

| Kind | Simple meaning |
|---|---|
| **Unclear** | A sentence that can be understood in two ways |
| **Missing** | Something important that is not written |
| **Clash** | Two requirements that say different things |
| **Cannot test** | We cannot check if it is done |

## 3. Suggestions and Decisions

| No. | Kind | Requirement | What is wrong | What we will do | Decision | Why |
|:---:|---|---|---|---|:---:|---|
| 1 | Unclear | FR-02 (search) | It does not say if searching with part of a word works. | Allow search with part of a word. Capital and small letters are the same. | **Accept** | Users do not remember the full title. |
| 2 | Unclear | NFR-02 (easy to use) | "Without help" is not exact. | Test: after 1 hour of training, a new librarian issues and returns 5 books without help. | **Accept** | Now we can test it. |
| 3 | Cannot test | NFR-04 (99% working) | The library opening hours are not written anywhere. | Write the opening hours in the assumptions. Check the 99% every month. | **Accept** | We cannot check 99% without the hours. |
| 4 | Unclear | FR-08 (reminders) | It does not say when the reminder or the overdue notice is sent. | Reminder 2 days before the due date. Overdue notice on the day the book becomes overdue. | **Accept** | Now the time is clear and testable. |
| 5 | Missing | FR-04 (issue a book) | Nothing says how the due date is decided. | Say: the due date is set from the library loan period (see the assumptions). | **Accept** | Every issued book needs a due date. |
| 6 | Missing | Whole list | There is no way to renew (extend) a loan. | Do not add it now. | **Reject** | The case does not ask for it. We can add it later. |
| 7 | Missing | Whole list | There are no fines for late books. | Do not add it now. | **Reject** | The case asks only for overdue notices. Fines need payment, which is outside our project. |

## 4. Result

- **7** suggestions in total
- **5** accepted
- **2** rejected

## 5. What Changed?

The accepted suggestions are already written into `requirements-list.md` and `assumptions-and-constraints.md`.
