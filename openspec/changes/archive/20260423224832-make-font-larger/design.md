## Context

The Anki templates currently use a base font size of 16px, which has been reported as too small for optimal reading during acquisition sessions.

## Goals / Non-Goals

**Goals:**
- Update the base font size to 20px in `Styling.css`.
- Maintain visual hierarchy and legibility of existing elements.

**Non-Goals:**
- Changing the layout structure of the cards.
- Adding new font families.

## Decisions

### Update Base Font Size in `.card`
- **Decision**: Change `font-size: 16px;` to `font-size: 20px;` in the `.card` class.
- **Rationale**: The `.card` class serves as the container for the entire card content. Setting the font size here allows child elements to inherit the size, ensuring a consistent look and feel.

## Risks / Trade-offs

- **Risk**: Content might overflow on very small mobile screens.
- **Mitigation**: Anki's default mobile rendering handles basic scaling, and 20px is generally safe for modern smartphones.
