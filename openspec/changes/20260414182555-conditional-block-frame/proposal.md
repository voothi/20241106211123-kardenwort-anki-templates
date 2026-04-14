## Why

The "Source Destination" block on the Anki card back currently shows even if translations are missing, leading to an incomplete or broken layout. Ensuring the block only appears when at least one translation field (`SentenceDestination` or `SentenceDestination2`) is populated improves visual consistency.

## What Changes

- Add a conditional CSS class to the Source Destination table.
- The table will be hidden if BOTH `SentenceDestination` and `SentenceDestination2` are empty.
- If at least one of them contains data, the table will be shown.

## Capabilities

### New Capabilities
- `conditional-block-frame`: Ensures the translation block is hidden only when both translation fields are empty.

### Modified Capabilities

## Impact

- `basic-20240218092126\card-1\2.Back.template.anki`: The table's class list will be updated with conditional logic.
