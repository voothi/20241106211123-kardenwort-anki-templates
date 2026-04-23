## ADDED Requirements

### Requirement: Increased Base Font Size
The Anki card templates SHALL use a base font size of 20px to ensure legibility across various screen sizes and reading distances.

#### Scenario: Verify base font size
- **WHEN** the Anki card is rendered
- **THEN** the `.card` class should have a `font-size` property set to `20px`

### Requirement: Consistent Scaling for Cloze Deletions
Cloze deletions SHALL remain prominently visible and legible when the base font size is increased.

#### Scenario: Verify cloze legibility
- **WHEN** a cloze deletion (`.cloze`) is rendered within a card
- **THEN** it should inherit the larger base font size and maintain its bold weight and color formatting.
