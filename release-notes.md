# Release Notes

## [v1.42.2] - 2026-01-13

### Added
- **Intelligent Word Highlighting**: New JavaScript feature in the Basic Front template that identifies and highlights occurrences of `WordSourceInflectedForm` words within the `SentenceSource`.
- **Unicode Support**: Highlighting works seamlessly with English, German, Russian, Ukrainian, and other languages.
- **AnkiDroid Compatibility**: Optimized scripts ensure highlighting works on mobile devices.

### Changed
- **Improved Context Focus**: In the Basic card type, the source sentence is now dimmed when a primary word is being studied, making the target word stand out more clearly.
- **Enhanced Template Structure**: Added unique IDs and conditional styling hooks to the HTML structure for better scriptability and customization.
