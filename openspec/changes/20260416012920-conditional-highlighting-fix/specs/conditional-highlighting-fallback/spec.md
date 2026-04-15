## ADDED Requirements

### Requirement: Fallback styles for highlight targets
The system SHALL apply visual styling properties allowing substring highlighting when fallback `WordSourceInflectedForm` variables are used in place of missing `WordSource` ones.

#### Scenario: WordSource is missing but WordSourceInflectedForm is present
- **WHEN** the primary word source field is empty and the inflected form field is populated
- **THEN** the parent sentence container adopts the `context` CSS style class.
- **THEN** the inflected form's specific container inherits standard text styling by omitting the explicit `context` CSS class rendering it in neutral white instead of gray.
