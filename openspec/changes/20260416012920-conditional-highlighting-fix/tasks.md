## 1. Conditionally Dim SentenceSource Container

- [ ] 1.1 In `basic-20240218092126\card-1\1.Front.template.anki`, update the `<span id="sentence-source">` tag to conditionally adopt the `class="context"` CSS class either when `WordSource` is provided, OR when `WordSource` is empty but `WordSourceInflectedForm` is available.

## 2. Brighten Primary WordSourceFallback 

- [ ] 2.1 In `basic-20240218092126\card-1\1.Front.template.anki`, modify the `<span class="context">` wrapper framing `WordSourceInflectedForm`. It should be rewritten to conditionally adopt `class="context"` exclusively when `WordSource` is provided. This will ensure that when it acts as a fallback for a missing primary `WordSource`, it is presented in standard/neutral white text instead of a dimmed appearance.
