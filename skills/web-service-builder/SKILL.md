---
name: web-service-builder
description: "Build practical web pages, landing pages, dashboards, small web apps, and service prototypes from requirements through implementation, responsive UI checks, Playwright verification, security review, and preview deployment preparation. Use when asked to create or improve a website, web service, React/Next.js app, teaching page, portfolio page, or interactive web tool."
---

# Web Service Builder

## Workflow

1. Clarify the user goal only if the product, audience, or required behavior is ambiguous enough to affect the build.
2. Inspect the existing project before choosing frameworks or patterns.
3. Implement the actual usable page or workflow as the first screen. Avoid placeholder landing pages unless the user asks for marketing copy.
4. Design for the domain: service tools should be quiet and efficient; teaching pages should be clear and navigable; game-related pages may be more visual and interactive.
5. Verify responsive layout, core interactions, empty/error/loading states, and text fit.
6. Use Playwright or browser verification when a local app can run.
7. Before deployment, check environment variables, secrets handling, accessibility basics, and broken links.

## Defaults

- Prefer the existing project stack.
- If starting fresh, prefer React or Next.js only when it fits the request.
- Keep UI controls complete and predictable: buttons, forms, tabs, filters, menus, and states should work.
- Avoid decorative excess that does not help the user inspect or use the service.
- For teaching or portfolio pages, make the subject visible immediately.
- For service prototypes, prioritize real workflows over marketing sections.

## Verification Checklist

- Desktop and mobile layouts do not overlap or clip text.
- Primary user flow works from start to finish.
- Buttons and forms have meaningful states.
- Console has no obvious runtime errors.
- Build or test command passes when available.
- Playwright smoke test covers the core path when practical.

## References

Read `references/web-build-checklist.md` when creating a new page/app or preparing a preview deployment.
