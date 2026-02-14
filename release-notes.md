# Release Notes

## [v1.46.4] - 2026-02-14

### Added
- **Sentence Fallback Logic**: Added support for phrase cards to use `SentenceDestination` as a fallback when `SentenceDestination2` is empty (display, TTS, and metadata).
- **Automatic Vocabulary Expansion**: Implemented logic to automatically expand `SentenceDestination2` on vocabulary cards if the primary `SentenceDestination` is empty.

### Fixed
- **Missing Audio Handling**: Improved TTS selection on phrase cards to intelligently switch to fallback sentences when primary audio sources are missing.


## [v1.46.2] - 2026-02-14

### Added
- **Destination Highlighting**: Implemented word and phrase highlighting for `SentenceDestination` and `SentenceDestination2`.
- **Automatic Highlighting Fallback**: Introduced a smart algorithm that automatically highlights the approximate target area in translation sentences based on the source word's position.
- **Phrase Support**: Highlighting logic now supports multi-word phrases in destination fields using a semicolon (`;`) separator.
- **Dimmed Styling**: Enhanced visual focus by dimming destination sentences and making highlighted words stand out with bright colors.

### Changed
- **Generic Highlighting Engine**: Refactored JavaScript highlighting logic into a flexible `highlightField` function supporting custom delimiters and target selectors.

## [v1.42.2] - 2026-01-13

### Added
- **Intelligent Word Highlighting**: New JavaScript feature in the Basic Front template that identifies and highlights occurrences of `WordSourceInflectedForm` words within the `SentenceSource`.
- **Unicode Support**: Highlighting works seamlessly with English, German, Russian, Ukrainian, and other languages.
- **AnkiDroid Compatibility**: Optimized scripts ensure highlighting works on mobile devices.

### Changed
- **Improved Context Focus**: In the Basic card type, the source sentence is now dimmed when a primary word is being studied, making the target word stand out more clearly.
- **Enhanced Template Structure**: Added unique IDs and conditional styling hooks to the HTML structure for better scriptability and customization.
