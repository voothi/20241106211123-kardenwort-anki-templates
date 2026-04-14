## 1. Implement Sentence Block Visibility (Completed)

- [x] 1.1 Modify `<table class="fixed-table">` at line 157 in `2.Back.template.anki`.
- [x] 1.2 Add the conditional class: `{{^SentenceDestination}}{{^SentenceDestination2}} field-hide{{/SentenceDestination2}}{{/SentenceDestination}}`.

## 2. Implement Word Block Visibility

- [x] 2.1 Remove the `{{#WordDestination}}` opening tag at line 15.
- [x] 2.2 Remove the `{{/WordDestination}}` closing tag at line 155.
- [x] 2.3 Modify `<table class="fixed-table">` at line 16.
- [x] 2.4 Add the conditional class: `{{^WordDestination}}{{^WordEnglish}}{{^WordGerman}}{{^WordUkrainian}}{{^WordSourceMorphologyAI}} field-hide{{/WordSourceMorphologyAI}}{{/WordUkrainian}}{{/WordGerman}}{{/WordEnglish}}{{/WordDestination}}`.

## 3. Verification

- [x] 3.1 Verify that the `field-hide` class effectively hides the table in Anki (CSS `display: none`).
