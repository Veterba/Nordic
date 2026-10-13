## Chat replies

Be terse, but keep everything relevant. Critique my ideas freely and avoid sycophancy. I want an honest appraisal.
When you pick between options, say why in one or two lines.

Exception: files, code comments, commit messages and docs are written in normal sentence case, plain and clear. The style above applies only to chat replies.

---

## Project
NordicSync AS (Moss, Norway): marketing and service website for a small digital agency (websites, automation, digital marketing, Sidy).
Scope of my work: **frontend only**. Never touch the backend, hosting, DNS, secrets or analytics accounts.

Stack: <fill in after discovery: framework, bundler, language, CSS approach, routing, i18n>.

Checks before saying something is done: <fill in real commands, e.g. `npm run typecheck`, `npm run lint`, `npm test`, `npm run build`>.

The current task is described in `TZ_nordicsync_frontend.md`. The reference prototype is `reference/site_c.html`: a design reference, not production code.
For a rebuild task, the TZ overrides section "Surgical Changes" below. Everything else here still applies.

---

## Design rules (short; details in the TZ)
- Palette: graphite plus one signal colour (`--sig`). Use the signal colour sparingly. All colours are CSS custom properties.
- One typeface: Familjen Grotesk (400/500/600), self-hosted. No hotlinked Google Fonts. No serif, no monospace.
- Large surfaces have square corners. Only small elements (buttons, fields, chips, small cards) are rounded.
- No stock photos, no AI-looking gradients, no emoji.
- Shader on the left hero panel only. Nothing heavy on the right.
- Never invent content: prices, claims, testimonials, client names, statistics. Use a visible `[PLACEHOLDER]` and list it in `CONTENT_TODO.md`.

---

## Git
- NEVER commit or push. Only I commit. You can stage, merge, resolve conflicts.
- One branch at a time. For a new feature, make a new branch.
- You may merge main INTO a feature branch to keep it up to date. I merge feature branches into main and delete them.
- When a feature is ready, tell me and suggest a commit message in the form `<type>: what changed` (feat, fix, style, docs, chore).

---

## Scratch files
Temporary files go to the OS temp dir or a gitignored folder, never to the repo root or my home folder. Clean them up when done.
Screenshots meant for review go to `docs/screens/`.

---

## Linear
NEVER create, update, or manage Linear issues/projects yourself. Only help identify where things should go and help draft content. I will create and update them manually.

---

## 1. Think Before Coding

Don't assume. Don't hide confusion. Surface tradeoffs.

Before implementing:
- State your assumptions explicitly. If uncertain, ask.
- If multiple interpretations exist, present them. Don't pick silently.
- If a simpler approach exists, say so. Push back when warranted.
- If something is unclear, stop. Name what's confusing. Ask.

## 2. Simplicity First

Minimum code that solves the problem. Nothing speculative.

- No features beyond what was asked.
- No abstractions for single-use code.
- No "flexibility" or "configurability" that wasn't requested.
- No error handling for impossible scenarios.
- If you write 200 lines and it could be 50, rewrite it.
- No new dependency without asking me first.

Ask yourself: "Would a senior engineer say this is overcomplicated?" If yes, simplify.

## 3. Surgical Changes

Touch only what you must. Clean up only your own mess.

When editing existing code:
- Don't "improve" adjacent code, comments, or formatting.
- Don't refactor things that aren't broken.
- Match existing style, even if you'd do it differently.
- If you notice unrelated dead code, mention it. Don't delete it.

When your changes create orphans:
- Remove imports/variables/functions that YOUR changes made unused.
- Don't remove pre-existing dead code unless asked.

The test: every changed line should trace directly to my request.

Exception: when the task is explicitly a rebuild or refactor, follow its spec instead.

## 4. Goal-Driven Execution

Define success criteria. Loop until verified.

Transform tasks into verifiable goals:
- "Add validation" becomes "Write tests for invalid inputs, then make them pass"
- "Fix the bug" becomes "Write a test that reproduces it, then make it pass"
- "Build the page" becomes "It renders at 1440, 1024 and 390 px, has no console errors, and passes the checks above"

For multi-step tasks, state a brief plan:
1. [Step] -> verify: [check]
2. [Step] -> verify: [check]

For anything visual, look at the actual screenshot before claiming it is done. If something could only be verified on a real GPU or a real phone, say that explicitly. Do not claim visual quality you did not inspect.

---

These guidelines are working if: fewer unnecessary changes in diffs, fewer rewrites due to overcomplication, and clarifying questions come before implementation rather than after mistakes.
