## Why

The "Source Destination" block on the Anki card back currently shows even if translations are missing, leading to an incomplete or broken layout. Ensuring the block only appears when all necessary translation fields are present improves readability and visual consistency.

## What Changes

- Wrap the Source Destination block (the translation table) in conditional checks for both `SentenceDestination` and `SentenceDestination2`.
- Ensure the block is hidden if at least one of these fields is empty.

## Capabilities

### New Capabilities
- `conditional-block-frame`: Ensures the translation block is only visible when both `SentenceDestination` and `SentenceDestination2` fields contain data.

### Modified Capabilities

## Impact

- `basic-20240218092126\card-1\2.Back.template.anki`: The table containing the sentence translations will be wrapped in conditional tags.
