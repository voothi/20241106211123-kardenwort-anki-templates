## Why

The "Source Destination" and "Word" blocks on the Anki card back currently show even if translations are missing or depend on a single field, leading to an incomplete or broken layout. Ensuring these blocks only appear when at least one relevant data field is populated improves visual consistency.

## What Changes

- Add conditional CSS classes to both the Sentence translation table and the Word translation table.
- **Sentence Table**: Hide if BOTH `SentenceDestination` and `SentenceDestination2` are empty.
- **Word Table**: Hide if ALL relevant fields (`WordDestination`, `WordEnglish`, `WordGerman`, `WordUkrainian`, `WordSourceMorphologyAI`) are empty.
- Remove the rigid `{{#WordDestination}}` wrapper around the word table.

## Capabilities

### New Capabilities
- `conditional-block-frame`: Ensures both sentence and word blocks are hidden only when all their respective data fields are empty.

### Modified Capabilities

## Impact

- `basic-20240218092126\card-1\2.Back.template.anki`: Both translation tables will have updated conditional logic for visibility.
