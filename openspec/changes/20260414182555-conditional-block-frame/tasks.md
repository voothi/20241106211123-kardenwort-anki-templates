## 1. Implement Conditional Visibility

- [ ] 1.1 Modify `<table class="fixed-table">` at line 157 in `2.Back.template.anki`.
- [ ] 1.2 Add the conditional class: `{{^SentenceDestination}}{{^SentenceDestination2}} field-hide{{/SentenceDestination2}}{{/SentenceDestination}}`.

## 2. Verification

- [ ] 2.1 Verify that the `field-hide` class effectively hides the table in Anki (CSS `display: none`).
