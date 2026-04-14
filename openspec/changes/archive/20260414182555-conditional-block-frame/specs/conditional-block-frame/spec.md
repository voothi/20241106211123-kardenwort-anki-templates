## ADDED Requirements

### Requirement: Conditional Visibility of Translation Blocks
The translation tables must be hidden if and only if all their respective data fields are empty.

#### Scenario: Sentence block logic
- **WHEN** `SentenceDestination` and `SentenceDestination2` are BOTH empty
- **THEN** The sentence table is hidden.

#### Scenario: Word block logic
- **WHEN** `WordDestination`, `WordEnglish`, `WordGerman`, `WordUkrainian`, and `WordSourceMorphologyAI` are ALL empty
- **THEN** The word table is hidden.

#### Scenario: Word block with partial data
- **WHEN** `WordDestination` is empty but `WordEnglish` is non-empty
- **THEN** The word table is displayed.
