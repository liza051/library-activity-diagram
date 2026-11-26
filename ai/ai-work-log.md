# AI Work Log — Library Activity Diagram

## 1. Purpose of AI Usage

AI was used as a supporting tool to analyze the business process, identify possible gaps in the Activity Diagram, and review consistency between the specification, diagram, and audit.

AI was not treated as the source of project requirements. Final decisions were made by the student.

## 2. AI Interaction Records

### Interaction 1: Activity Diagram Review

**Task given to AI (summary):** Review the Activity Diagram for the book reservation process and check whether it includes the required branching, parallel activities, and message communication.

**AI response (summary):** AI reviewed the three reservation scenarios and identified that the notification message should explicitly show that the Reader receives it.

**Student's evaluation:** The recommendation was accepted. An additional activity representing receipt of the confirmation message was added.

### Interaction 2: Specification Consistency

**Task given to AI (summary):** Check whether the specification describes the same activities and message communication as the Activity Diagram.

**AI response (summary):** AI identified that the specification did not explicitly describe the Reader receiving the notification.

**Student's evaluation:** The recommendation was accepted. Sections 5 and 7 of the specification were updated to clarify message communication and the selected modeling notation.

### Interaction 3: Audit Review

**Task given to AI (summary):** Review the Activity Diagram audit and check whether the message communication description matches the diagram.

**AI response (summary):** AI identified that the audit described the notification branch as ending immediately after sending the message.

**Student's evaluation:** The recommendation was accepted. The audit was updated to include message receipt and continuation to the synchronization point.

### Interaction 4: DEFENSE Review

**Task given to AI (summary):** Review DEFENSE.md for consistency with the Activity Diagram and the laboratory requirements.

**AI response (summary):** AI recommended explicitly mentioning that the Reader receives the confirmation notification and correcting a typographical error.

**Student's evaluation:** Both corrections were accepted and applied.

## 3. Student's Final Decisions

The student reviewed the AI recommendations and made the following decisions:

- Kept the UML Activity Diagram with Mermaid flowchart syntax.
- Preserved the three reservation scenarios: SC-01, SC-02, and SC-03.
- Kept the parallel execution of the BookCopy status update and notification delivery.
- Added an explicit activity showing that the Reader receives the confirmation message.
- Updated the specification, audit, and DEFENSE.md to maintain consistency.

## 4. Responsibility

AI was used for analysis, feedback, and documentation review.

The student evaluated the recommendations, decided which changes to apply, and remains responsible for the final project artifacts.

*Note: The interaction records above are summaries of the work process, not verbatim transcripts of the prompts and responses.*