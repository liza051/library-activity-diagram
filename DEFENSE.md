# DEFENSE — Library Activity Diagram

## 1. Intent and Acceptance Criteria

The purpose of this project is to describe the business process **Reserve a Book Copy** using a UML Activity Diagram implemented with Mermaid flowchart syntax.

The diagram represents three reservation scenarios: successful reservation, no available book copies, and an already reserved book copy. It includes conditional branching, parallel activities, synchronization, and message communication.

## 2. Modeling Decisions

### Selected Modeling Notation

The Activity Diagram was selected because it clearly represents the sequence of business activities, conditional decisions, parallel execution, and synchronization.

Mermaid flowchart syntax was used because it allows the diagram to be maintained as a declarative text file and rendered for review.

### Process Participants

The process includes the following participants:
- Reader
- ReservationUI
- ReservationService
- BookCopy
- Reservation
- NotificationService

Each participant has a defined responsibility in the reservation process.

### Process Scenarios

The diagram represents three scenarios:

- **SC-01 — Successful reservation:** the system creates a reservation, updates the book copy status, and sends a confirmation notification.
- **SC-02 — No available book copies:** the system informs the reader that no copies are available, and no reservation is created.
- **SC-03 — Selected book copy is already reserved:** the system rejects the request and informs the reader.

## 3. Parallel Activities and Message Communication

After a successful reservation is created, two activities are performed in parallel:

1. Updating the BookCopy status to `reserved`.
2. Sending a confirmation notification to the Reader.

The NotificationService sends the confirmation message, and the Reader receives it.

Both activities must be completed before the process continues through the Join node.

The system does not wait for the Reader to read or respond to the notification.

## 4. Audit and Discrepancies

The audit identified three differences between the Activity Diagram and the previous sequence diagrams:

1. The BookCopy status update is represented as a separate activity.
2. NotificationService is explicitly represented as a separate participant.
3. Parallel execution and synchronization are explicitly shown.

These details provide a more detailed representation of the business process. The previous Lab 3 artifacts remain unchanged.

## 5. Verification Results

The Activity Diagram was reviewed according to the following criteria:

- All three reservation scenarios are represented.
- Conditional branches have explicit outcomes.
- Each scenario reaches a defined ending point.
- The successful scenario includes two parallel activities.
- The Join node synchronizes both parallel branches.
- Message communication identifies the sender and receiver.
- The process does not wait for a response from the Reader.

The source diagram and its rendered image are stored in the `activity/` directory.

## 6. Conclusion

The project provides an Activity Diagram for the Library Reservation System.

The diagram describes the reservation process, its alternative scenarios, parallel activities, synchronization, and notification communication.

The model is based on UC-01 from Lab 2 and extends the process description from Lab 3 with additional activity-level details.