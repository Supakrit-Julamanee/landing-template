---
name: landing
description: Run the full landing-page client job end to end — brief → spec → build → QA → delivery — in one command.
argument-hint: "[path-to-brief.md or brief text] [--auto]"
disable-model-invocation: true
---

# Landing page: full workflow

Input: $ARGUMENTS
(A path to a brief file, or the brief pasted as text. `--auto` = skip the spec approval checkpoint.)

Run every phase below in order without waiting to be told to continue. Stop ONLY at the two checkpoints marked ⛔.
Keep a running log in `docs/progress.md` (phase, what was done, open issues) so work can resume after a break.

## Phase 1 — Intake
1. Read the brief. Extract: business, target audience, main goal/CTA, sections wanted, brand (logo, colors, fonts), language (TH / EN / both), contact/form destination, deadline, references.
2. If anything essential is missing (CTA, language, brand colors), ask ALL missing questions at once in a single message. Otherwise use sensible defaults and list them as assumptions.

## Phase 2 — Spec
1. Write `docs/spec.md`: page goal, section list in order, copy outline per section (headline + subline + CTA text), color/typography tokens, assets needed from client, assumptions.
2. ⛔ Checkpoint 1: show a short summary of the spec and ask for approval — unless `--auto` was passed, in which case continue.

## Phase 3 — Build
1. Scaffold the project using the default stack in CLAUDE.md (unless the brief specifies another). Init git and commit.
2. Set up design tokens (colors, fonts, spacing) first, then build sections top to bottom as reusable components.
3. Write final copy in the requested language(s). Use placeholder images with clear `TODO: client asset` markers — never pull copyrighted images.
4. Add: SEO meta, Open Graph/Twitter tags, favicon, semantic HTML, alt text, working contact form or CTA link, analytics placeholder.
5. Commit after each major section.

## Phase 4 — QA loop (max 3 rounds)
1. Run the build; fix any errors.
2. Start the dev server and delegate a full check to the `landing-qa` subagent, passing the local URL.
3. Fix every issue it reports marked High or Medium. Re-run QA.
4. Stop after the report is clean or after 3 rounds; list anything left unresolved.

## Phase 5 — Delivery
1. Write `docs/delivery.md` for the client (in the brief's language): what was built, how to edit text/images, Lighthouse scores, assets still needed, next steps.
2. Final commit with a clear message.
3. ⛔ Checkpoint 2: ask whether to deploy (and where). Never deploy to production without explicit approval.

## Final report to me
Summarise in under 10 lines: what was built, QA scores, open TODOs, and the exact command to preview locally.
