## Why

When the primary `WordSource` field is empty but the `WordSourceInflectedForm` field is populated, the Anki template fails to render the fallback values correctly. Specifically, the highlighting style is lost because the `context` CSS class is not applied to the `SentenceSource` container, making both the base text and the `<u>` highlighted text solid white. This prevents users from seeing the highlighted inflected words in context and forces an all-white sentence rendering without any visible highlighting distinctions. Additionally, the fallback word should be rendered as plain text (white) instead of context text (gray).

## What Changes

- Modify `#sentence-source` to inherit the `context` CSS class when `WordSourceInflectedForm` is populated even if `WordSource` is absent.
- Update the layout structure surrounding `WordSourceInflectedForm` so that it renders the primary white text styling instead of the dimmed `context` style when it is used as a fallback for the missing `WordSource`.
- Ensure all rendering conditions (`WordSource`, `WordSourceInflectedForm`, `WordSourceIPA`, `WordSourceAudio`) properly encapsulate the visible block so the Anki card layout remains intact.

## Capabilities

### New Capabilities

- `conditional-highlighting-fallback`: Introduce logic for the `1.Front.template.anki` file to correctly identify and style fallback text sources when primary fields are empty, ensuring visual contrast for highlighting works regardless of the source.

### Modified Capabilities

## Impact

- `card-1\1.Front.template.anki` layout and conditional statements.
