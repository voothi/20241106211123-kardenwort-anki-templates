## ADDED Requirements

### Requirement: Conditional Visibility of Translation Block
The translation table must be hidden if and only if both translation fields are empty.

#### Scenario: Both fields present
- **WHEN** `SentenceDestination` is non-empty AND `SentenceDestination2` is non-empty
- **THEN** The table is displayed.

#### Scenario: Only one field present (1)
- **WHEN** `SentenceDestination` is non-empty AND `SentenceDestination2` is empty
- **THEN** The table is displayed (showing only the first translation).

#### Scenario: Only one field present (2)
- **WHEN** `SentenceDestination` is empty AND `SentenceDestination2` is non-empty
- **THEN** The table is displayed (showing only the second translation).

#### Scenario: Both fields missing
- **WHEN** `SentenceDestination` is empty AND `SentenceDestination2` is empty
- **THEN** The table is hidden (e.g., via `field-hide` class).
