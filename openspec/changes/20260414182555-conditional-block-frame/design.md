## Context

The Anki template contains two translation tables: one for sentences (lines 157-349) and one for words (lines 15-155). Both need robust visibility logic to avoid rendering empty "frames" when data is missing across multiple optional fields.

## Goals / Non-Goals

**Goals:**
- Hide the sentence table if `SentenceDestination` AND `SentenceDestination2` are both empty.
- Hide the word table if `WordDestination`, `WordEnglish`, `WordGerman`, `WordUkrainian`, AND `WordSourceMorphologyAI` are all empty.
- Maintain minimal code duplication.

## Decisions

- **Sentence Block**: Already implemented with a nested conditional class `{{^SentenceDestination}}{{^SentenceDestination2}} field-hide{{/SentenceDestination2}}{{/SentenceDestination}}`.
- **Word Block**: 
  - Remove the `{{#WordDestination}}` guard at line 15 and its closing tag at line 155.
  - Add a nested conditional class to the `<table>` at line 16: `{{^WordDestination}}{{^WordEnglish}}{{^WordGerman}}{{^WordUkrainian}}{{^WordSourceMorphologyAI}} field-hide{{/WordSourceMorphologyAI}}{{/WordUkrainian}}{{/WordGerman}}{{/WordEnglish}}{{/WordDestination}}`.

## Risks / Trade-offs

- **Risk**: The Word block is very large; removing the `{{#WordDestination}}` tag might reveal empty placeholders if none of the other fields are present either. The nested conditional class mitigates this by hiding the entire table if everything is empty.
