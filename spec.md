# Specification — Library Reservation Process

## 1. Process Intent

The purpose of this specification is to describe the business process **Reserve a Book Copy** (UC-01) using a UML Activity Diagram.

The process covers the submission and validation of a reservation request, reservation creation, book copy status update, and notification to the reader.

## 2. Process Participants and Roles

- **Reader** — selects a book copy and submits a reservation request.
- **ReservationUI** — receives the request and displays the result.
- **ReservationService** — validates the request and manages the reservation process.
- **BookCopy** — represents the physical book copy and its current status.
- **Reservation** — represents the reservation record.
- **NotificationService** — sends reservation notifications to the reader.

## 3. Process Preconditions

- The reader is registered in the library system.
- The reader has selected a book copy.
- The reservation system is available.

## 4. Process Steps and Branching

1. The Reader selects a book copy.
2. The Reader submits a reservation request through ReservationUI.
3. ReservationService receives and validates the request.
4. The system checks whether available book copies exist.

### SC-02: No available book copies
- If no copies are available, the system rejects the request.
- ReservationUI displays a message that no copies are available.
- No reservation is created.
- The process ends.

### SC-03: Selected book copy is already reserved
- If the selected copy is already reserved, the system rejects the request.
- ReservationUI displays an already-reserved message.
- No new reservation is created.
- The process ends.

### SC-01: Successful reservation
- If the selected copy is available, ReservationService creates a Reservation record linked to the Reader and BookCopy.
- After successful creation, two activities begin in parallel:
  1. ReservationService updates the BookCopy status to `reserved`.
  2. NotificationService sends a confirmation message to the Reader.
- The notification is sent without waiting for a response from the Reader.
- After both activities are completed, the parallel branches join.
- ReservationUI displays the successful reservation confirmation.
- The process ends.

## 5. Message Communication

- **Sender:** NotificationService.
- **Receiver:** Reader.
- **Message:** Reservation confirmation.
- **Process behavior:** The notification is sent without waiting for the Reader's response. The process continues and completes after the parallel activities join.

## 6. Parallel Activities

After creating a reservation, the process executes two independent activities in parallel:
- Updating the physical book copy status.
- Sending a confirmation notification.

A synchronization point joins both branches before the process ends.

## 7. Selected Modeling Form

**UML Activity Diagram using Mermaid flowchart syntax.**

This form was selected because it clearly represents business process activities,