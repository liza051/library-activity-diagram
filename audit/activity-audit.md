# Activity Diagram Audit

## 1. Transition Completeness

All process paths have defined transitions from the start node to an end node.

The diagram includes three scenarios:
- SC-01: Successful reservation.
- SC-02: No available book copies.
- SC-03: Selected book copy is already reserved.

No scenario is intentionally left without an ending point.

## 2. Branching and Conditions

The process contains two decision points:
- Availability of book copies.
- Availability of the selected book copy.

Each decision has explicit Yes and No outcomes. The unsuccessful scenarios end without creating a reservation.

## 3. Parallel Activities and Synchronization

After a successful reservation, two activities execute in parallel:
- Updating the BookCopy status to `reserved`.
- Sending a confirmation notification to the Reader.

Both branches lead to the Join node. The process continues after both activities are completed.

The process does not wait for the Reader to read or respond to the notification.

## 4. Message Communication

- Sender: NotificationService.
- Receiver: Reader.
- Message: Reservation confirmation.
- Expected behavior: the notification is sent without waiting for a response.

The notification branch is completed when the message is sent.

## 5. Top 3 Discrepancies and Resolutions

### Discrepancy 1: BookCopy status update

The Lab 3 sequence diagram checks the availability of a book copy but does not explicitly show its status update after a successful reservation.

**Resolution:** The Activity Diagram includes a separate activity that updates the BookCopy status to `reserved`. This makes the business process more detailed.

### Discrepancy 2: NotificationService representation

The Lab 3 sequence diagram shows the confirmation message through ReservationUI but does not include a separate NotificationService participant.

**Resolution:** The Activity Diagram explicitly represents NotificationService as the sender of the confirmation message to the Reader. This clarifies message communication.

### Discrepancy 3: Parallel execution

The Lab 3 sequence diagram does not explicitly represent the parallel execution of the book copy status update and notification delivery.

**Resolution:** The Activity Diagram includes two parallel activities and a Join node. The process continues after both activities are completed, without waiting for the Reader to respond to the notification.

## 6. Consistency with Previous Labs

The Activity Diagram follows UC-01 and its three scenarios from Lab 2.

It is based on the reservation process described in the Lab 3 sequence diagrams.

The Activity Diagram provides additional detail about the BookCopy status update, notification delivery, and parallel execution. These details are explicitly documented as differences in this audit.

The Lab 3 artifacts remain unchanged.