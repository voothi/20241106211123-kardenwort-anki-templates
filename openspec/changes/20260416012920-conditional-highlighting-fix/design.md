## Context

The current `1.Front.template.anki` template visually dims the main `SentenceSource` block by applying a CSS class `context` when a `WordSource` is present. This makes high-contrast white highlighted words visually distinguishable. However, when the primary `WordSource` is missing and a `WordSourceInflectedForm` acts as a fallback, this conditional `context` class fails to apply. This results in the highlighted words blending invisibly into the default white text of `#sentence-source` rendering highlights practically useless and visually jarring. In addition, `WordSourceInflectedForm` had a hardcoded `context` class making it gray, hiding the fact it was acting as the primary word.

## Goals / Non-Goals

**Goals:**
- Dynamically apply the `.context` CSS class to the `#sentence-source` container if `WordSourceInflectedForm` is populated, even when `WordSource` is empty.
- Ensure the fallback string itself (the `WordSourceInflectedForm`) is styled neutrally (solid white instead of grey) when used as the primary substitution.

**Non-Goals:**
- Rewriting the dynamic Javascript highlighting regex engine or algorithms (we are only touching standard Anki `{{#Cond}}` template flags).

## Decisions

- **Modify `SentenceSource` condition**: Instead of checking `{{#WordSource}}class="context"{{/WordSource}}` we expand the check to evaluate `WordSourceInflectedForm` exclusively when `WordSource` is absent in `class="..."`. 
- **Remove hardcoded `context` from fallback term container**: The container for `WordSourceInflectedForm` will now conditionally render `class="context"` only if `WordSource` explicitly exists. This ensures it looks like primary text when it acts as primary text.

## Risks / Trade-offs

- *Complexity of nested conditionals*: Applying anki handlebars inside HTML tags `class="{{#WordSource}}context{{/WordSource}}{{^WordSource}}{{#WordSourceInflectedForm}}context{{/WordSourceInflectedForm}}{{/WordSource}}"` is slightly dense but handles all edge cases cleanly without breaking existing DOM structure references.
