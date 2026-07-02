# teach-me

**The best personal AI teaching companion, synthesized from the world's greatest educators and learning science.**

A stateful, workspace-based teaching skill for Grok (and compatible agents). It turns any folder into a rigorous, long-term personal "course" for deep learning.

**Reviewed & improved (2026-07)** against:
- Anthropic Superpowers "writing-skills" (TDD for skills, SDO, description discipline, red flags/rationalization tables, pressure testing mindset, token efficiency, structure guidelines).
- Official Grok skill authoring (08-skills.md + create-skill best practices).
- Skill-creator patterns (progressive disclosure, clear anatomy, third-person triggers).
- Additional patterns from skill development communities (bulletproofing, one excellent example, symptom-focused descriptions).

All changes make the skill more discoverable, harder to shortcut, easier to follow precisely, and more resistant to common failure modes of AI teaching.

- Treats your current directory as the complete teaching environment.
- Produces beautiful, self-contained HTML lessons.
- Grounds everything in your real **Mission**.
- Builds **knowledge + skills + wisdom** using the most effective, research-backed methods known.
- Strong support for Indian learners/contexts while being universally excellent.
- Free. Personal educational use only. MIT licensed.

## Why This Skill Exists

Traditional AI "teaching" often gives shallow explanations, moves too fast, and forgets what you already know. This skill is different.

It is the result of distilling the methods of history's and today's most effective teachers and the strongest cognitive science, then packaging it as a reliable, repeatable agent behavior.

### Core Inspirations & Teachers (Synthesized, Not Copied)

**Matt Pocock** — Original "teach" skill structure (the elegant workspace model with MISSION.md, learning records as ADRs, lessons as HTML artifacts, RESOURCES, GLOSSARY, assets reuse, and the beautiful philosophy of knowledge → skills → wisdom). This project stands on his shoulders. Thank you, Matt.

**Richard Feynman** — The Feynman Technique: If you can't explain it simply, you don't understand it. Identify gaps by teaching a child. Use plain language and analogies. We embed "Feynman checkpoints" in lessons and require the learner (and AI) to surface simplifications.

**Sal Khan (Khan Academy)** — Mastery learning over test-passing. Self-paced progression only after demonstrated mastery. Bite-sized content + immediate feedback + interactive practice. Free, world-class education for anyone, anywhere. Teacher as guide, not sole lecturer. We enforce mastery gates and use tight feedback loops.

**Barbara Oakley** — *Learning How to Learn*. Focused vs diffuse modes. Chunking. The power of metaphors and analogies. Procrastination as the real enemy (use process). "Practice makes permanent." We design for both focused effort and diffuse reflection, encourage metaphors in explanations, and guard against over-fluency.

**Andrew Huberman (Huberman Lab)** — Neuroscience of learning in practice. 
- Short-to-medium intense focus bouts followed by testing.
- Sleep (especially REM) as non-negotiable for consolidation.
- NSDR (non-sleep deep rest / yoga nidra style) after learning sessions dramatically boosts retention.
- Emotion, storytelling, and active engagement strengthen memory.
- Limit deep work to ~3-4 focused hours/day + consistency beats marathon sessions.
We bake protocol recommendations directly into lesson structure and NOTES.

**Carol Dweck** — Growth Mindset. Abilities are developed through effort, strategies, and help. "Not yet" > failure. Praise process, strategies, and persistence. We use growth-mindset language in all feedback, learning records, and lesson tone. Normalize struggle as the path to stronger neural connections.

**Maria Montessori** — Respect for the child's (learner's) autonomy and natural development. Prepared environment. Sensitive periods. Auto-education (learning by doing with control of error). Mixed-age collaboration (here: building on prior records). The adult is a guide who prepares the environment and steps back. We treat the workspace as the "prepared environment", respect the learner's current zone via records, build interactive materials with built-in error detection/feedback, and prioritize intrinsic motivation and independence.

**Supporting Cognitive Science** (synthesized):
- Retrieval practice / Active Recall (Roediger, Karpicke, "testing effect")
- Spaced Repetition
- Interleaving (instead of blocking)
- Desirable Difficulties (Bjork)
- Dual Coding (text + visuals)
- Elaboration & concrete examples
- Formative assessment + immediate feedback

No single source was copied verbatim. All ideas are transformed into practical agent instructions and workflows tailored for long-term personal mastery.

Thank you to every educator, researcher, and practitioner whose public work made better learning accessible.

## Features (Best-in-Class)

- **Mission-driven**: Everything traces back to a concrete "Why" and success criteria. Missions evolve with evidence.
- **Learning Records** (like lightweight ADRs): Capture genuine understanding, prior knowledge, misconceptions corrected, and mission shifts. Used to compute true Zone of Proximal Development.
- **Beautiful, self-contained lessons** (`lessons/NNNN-*.html`): Tufte-inspired typography + modern learning UX. Every lesson includes active recall, Feynman prompt, primary source recommendation, and spaced-review cue.
- **Mastery before progress**: Interactive practice with tight loops. No advancing on vibes.
- **Science protocols built-in**: Post-lesson NSDR suggestion, sleep importance, interleaving guidance, emotion/story in examples.
- **Reference artifacts** (`reference/`) and evolving `GLOSSARY.md` (compressed, opinionated language of the domain).
- **High-trust RESOURCES.md** with annotation and gaps tracking.
- **Assets reuse**: Shared stylesheet, quiz widgets, diagrams — lessons compose, they don't duplicate.
- **India-aware (optional but excellent)**: Prioritizes trusted Indian resources and contexts when relevant (NPTEL, NCERT, UPSC patterns, Hinglish, cultural examples) without limiting global excellence.
- **NOTES.md** for learner preferences and teaching meta.
- **Long-term state**: The workspace *is* your personal university for that topic.

## Workspace Layout (Created Lazily)

```
.
├── MISSION.md                 # Your real-world why + success criteria
├── RESOURCES.md               # Curated, annotated high-trust sources + communities
├── GLOSSARY.md                # The canonical language of *this* topic (only after true understanding)
├── NOTES.md                   # Preferences, observations, meta
├── learning-records/
│   └── 0001-*.md ...          # Decision-grade insights + evidence
├── lessons/
│   └── 0001-*.html ...        # Primary teaching artifacts (beautiful + interactive)
├── reference/                 # Cheat sheets, diagrams, summaries (printable)
└── assets/                    # Reusable components (CSS, quiz JS, etc.)
```

## How to Use (as a Grok Skill)

1. Install the skill (copy `SKILL.md` + format files to `~/.grok/skills/teach-me/` or your project `.grok/skills/teach-me/`).
2. `cd` into a fresh or existing folder you want as your learning workspace.
3. Run `/teach-me "I want to master X because ..."` or just `/teach-me`.
4. The agent will:
   - Establish or refine your MISSION if missing.
   - Diagnose current level via records.
   - Curate/find resources.
   - Design and output the next tight lesson.
   - Create learning records when you demonstrate real understanding.
   - Suggest real-world practice + communities.

Lessons are designed to be opened directly in a browser (`open lessons/0001-foo.html`).

## Installation in Your Environment

```bash
# User-global
mkdir -p ~/.grok/skills/teach-me
cp SKILL.md MISSION-FORMAT.md RESOURCES-FORMAT.md GLOSSARY-FORMAT.md LEARNING-RECORD-FORMAT.md ~/.grok/skills/teach-me/

# Or project-local (recommended when version-controlling your learning)
mkdir -p .grok/skills/teach-me
cp ... .grok/skills/teach-me/
```

Then invoke with `/teach-me`.

The skill uses `disable-model-invocation: true` so it is primarily slash-command driven (you stay in control).

## License & Personal Use

See [LICENSE](./LICENSE).

MIT licensed so you have full freedom for personal modification.

**Explicit intent**: This is a free tool for **your personal education**. It is not intended for commercial resale, SaaS products, or paid courses built directly on this agent prompt without significant original transformation and attribution.

## Credits & Deep Gratitude

- **Matt Pocock** — Foundational skill architecture and philosophy. Original teach skill: https://github.com/mattpocock/skills
- **Richard Feynman** — For making the complex simple and insisting on real understanding.
- **Sal Khan & team** — For proving mastery + access at scale is possible and beautiful.
- **Barbara Oakley** — For demystifying *how* the brain actually learns.
- **Andrew Huberman** — For translating hard neuroscience into usable daily protocols anyone can apply.
- **Carol Dweck** — For the mindset shift that changes everything about struggle.
- **Maria Montessori** — For respect for the learner and the prepared environment.
- All the researchers behind retrieval practice, spacing, interleaving, and desirable difficulties.
- Every Indian educator, content creator, and platform (NPTEL, DIKSHA, great coaching teachers, etc.) who makes high-quality learning accessible in our context.

This skill would not exist without the public generosity of all the above.

## Contributing / Customizing

Fork it. Improve the formats. Add better quiz components. Extend the India or domain-specific guidance. Make even tighter lessons.

When you discover something that works brilliantly for you, consider adding a learning record (in your workspace) and perhaps a PR or note back here.

---

**Start learning like the best in the world learn.**

Run `/teach-me` in a clean folder and begin.
