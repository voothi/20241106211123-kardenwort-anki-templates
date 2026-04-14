## Context

The Anki template contains a "Source Destination" table (lines 157-349) that displays sentence translations. Currently, the table is displayed even if no translations are present. The user wants to hide this table ONLY if both translation fields are empty.

## Goals / Non-Goals

**Goals:**
- Hide the translation table if `SentenceDestination` AND `SentenceDestination2` are both empty.
- Show the table if either field is non-empty.

**Non-Goals:**
- Duplicating the table HTML structure.

## Decisions

- Use Anki's conditional tags to conditionally add the `field-hide` CSS class to the table element.
- The logic will be nested: `{{^SentenceDestination}}{{^SentenceDestination2}} field-hide{{/SentenceDestination2}}{{/SentenceDestination}}`.
- This avoids code duplication and keeps the change minimally invasive.

## Risks / Trade-offs

- **Risk**: Overlapping conditional logic inside the table. However, since we are only adding a class to the outer tag, it should not interfere with the internal rendering.
