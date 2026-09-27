# Project defaults — landing page (applies only inside this folder)

## Who I am
Frontend developer doing freelance landing pages for clients. Clients are mostly Thai; sites are Thai, English or both.

## Default stack (change here if you prefer another)
- Next.js (App Router) + TypeScript + Tailwind CSS
- Static export where possible; deploy target Vercel unless the brief says otherwise
- Fonts: next/font; Thai text → "Noto Sans Thai" or "IBM Plex Sans Thai" paired with a Latin font
- Icons: lucide-react. No heavy UI libraries unless needed.

## Project layout
- `docs/brief.md`, `docs/spec.md`, `docs/progress.md`, `docs/delivery.md`
- `src/components/sections/` — one file per section (Hero, Features, Testimonials, Pricing, FAQ, CTA, Footer)
- `src/content/` — all copy in one place (per language) so clients' text edits don't touch components

## Standards
- Mobile-first; test 375 / 768 / 1440
- Lighthouse ≥ 90 on all four categories
- Semantic HTML, one h1, alt text everywhere, visible focus states
- Images: next/image, WebP/AVIF, explicit sizes
- Never use copyrighted images or copy from other sites; use placeholders marked `TODO: client asset`
- Commit after each meaningful step with a clear message

## Working style
- For `/landing`, run the whole workflow autonomously and only stop at its checkpoints.
- Batch questions to me into one message rather than asking one at a time.
- Never deploy to production or push to a client's repo without my explicit OK.
