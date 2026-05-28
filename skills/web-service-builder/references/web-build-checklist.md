# Web Build Checklist

## Requirement Pass

- Who uses it?
- What do they need to accomplish first?
- What content or data is real versus placeholder?
- Is this for teaching, portfolio, internal tooling, or public service?

## UI Pass

- First screen contains the usable experience or the core offer.
- Navigation is obvious.
- Mobile layout is not an afterthought.
- Dense tools favor scanability over large decorative sections.
- Text fits inside controls and cards.

## Engineering Pass

- Follow existing package manager and scripts.
- Keep state local unless shared state is truly needed.
- Avoid adding dependencies for small utilities.
- Validate form inputs.
- Do not expose secrets in client code.

## Verification Pass

- Run build, lint, or tests if available.
- Use Playwright/browser for the primary interaction.
- Capture screenshots when visual quality matters.
- Prepare deployment notes for Vercel only when deployment is requested or clearly implied.
