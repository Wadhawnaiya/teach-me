# Assets — Reusable Components for teach-me Lessons

Lessons should **reuse** before inventing.

## Current

- `base-lesson.css` — Drop-in beautiful typography + lesson-specific components (Feynman boxes, recall prompts, simple quizzes, growth mindset callouts). Designed to be inlined or linked. Works in light/dark and prints well.

## How to Use in a Lesson

```html
<link rel="stylesheet" href="../assets/base-lesson.css">
```

Or copy the critical parts inline so the lesson remains fully self-contained forever.

## Building Good Interactive Elements

- Every lesson should have at least one **active recall** moment before "moving on".
- Prefer **exact same length answers** in multiple choice to remove formatting cues.
- Use simple vanilla JS for quizzes (no external dependencies).
- Include a "Explain this back to me like I'm 12" (Feynman) text area + guidance.
- Add a small "What did you notice?" reflection at the end.

## Future Ideas (contribute!)

- Reusable diagram helpers (SVG + labels)
- Spaced repetition mini-scheduler widget (localStorage dates)
- Simple simulator for the domain (e.g. physics sandbox, code runner if safe)
- Progress tracker that writes back to learning-records pattern

Remember: beauty + craft + low friction + real retrieval.
