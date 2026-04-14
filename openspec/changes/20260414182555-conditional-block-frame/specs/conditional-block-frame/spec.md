## ADDED Requirements

### Requirement: Conditional Visibility of Translation Block
The translation table must only be visible if both translation fields are populated.

#### Scenario: Both fields present
- **WHEN** `SentenceDestination` is non-empty AND `SentenceDestination2` is non-empty
- **THEN** The table with CSS class `fixed-table` (starting at line 157) is displayed.

#### Scenario: SentenceDestination missing
- **WHEN** `SentenceDestination` is empty
- **THEN** The entire translation table is hidden.

#### Scenario: SentenceDestination2 missing
- **WHEN** `SentenceDestination2` is empty
- **THEN** The entire translation table is hidden.
