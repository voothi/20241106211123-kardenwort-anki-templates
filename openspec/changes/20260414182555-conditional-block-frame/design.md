## Context

The Anki template contains a "Source Destination" table (lines 157-349) that displays sentence translations. Currently, the table is displayed even if only one of the translation fields (`SentenceDestination` or `SentenceDestination2`) is populated. This can lead to an incomplete visual "frame" on the card.

## Goals / Non-Goals

**Goals:**
- Hide the entire translation table if `SentenceDestination` is empty.
- Hide the entire translation table if `SentenceDestination2` is empty.
- Maintain minimal changes to the existing complex logic within the table.

**Non-Goals:**
- Refactoring the internal conditional logic of the table (TTS selection, checkboxes, etc.).

## Decisions

- Wrap the `<table>` element starting at line 157 in a nested conditional block:
  ```html
  {{#SentenceDestination}}
  {{#SentenceDestination2}}
  <table class="fixed-table">
    ...
  </table>
  {{/SentenceDestination2}}
  {{/SentenceDestination}}
  ```
- This ensures the table only renders if both fields are non-empty.

## Risks / Trade-offs

- **Risk**: If some cards are intentionally designed to have only one translation, those cards will now hide the translation table entirely. However, the user's request explicitly states that it should be hidden if "at least one ... is missing", implying both are required for this specific card type.
