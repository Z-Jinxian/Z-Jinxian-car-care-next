# AGENTS.md

## Project Overview

This is a single-page car wash and detailing website built with Next.js.

- Project name: `car-care-next`
- Framework: Next.js 15 with React 19
- Language: TypeScript
- Main page: `app/page.tsx`
- Global styles: `app/globals.css`
- Logo asset: `public/assets/logo.svg`
- Brand shown on page: 澄境汽车洗护中心
- Store address shown on page: 小米汽车旁 · 上海市浦东新区示例路 88 号
- Phone number shown on page: `400-888-6600`

## Current Page Content

The homepage includes:

- Sticky top navigation
- Brand logo and phone CTA
- Hero section for car wash and detailing services
- Store address callout near the hero copy
- Service cards
- Wash/detailing process section
- Pricing cards
- SVG-based service/gallery visuals
- Customer reviews
- Booking form with client-side toast confirmation
- Footer with address, hours, and phone number

## File Structure

```text
.
├── app/
│   ├── globals.css
│   ├── layout.tsx
│   └── page.tsx
├── public/
│   └── assets/
│       └── logo.svg
├── package.json
├── next.config.ts
├── tsconfig.json
└── AGENTS.md
```

## Common Commands

Install dependencies first if `node_modules` is missing:

```bash
npm install
```

Run locally:

```bash
npm run dev
```

Build for production:

```bash
npm run build
```

Start production server after build:

```bash
npm run start
```

Lint script exists in `package.json`:

```bash
npm run lint
```

## Implementation Notes

- `app/page.tsx` is a client component because it uses `useState` for the booking form toast.
- Most page data is stored as arrays near the top of `app/page.tsx`.
- `app/globals.css` contains all layout, responsive, and visual styling.
- The logo should be referenced as `/assets/logo.svg` from React/Next files.
- The page uses inline SVG illustrations for the gallery; no external image CDN is required.
- The design is responsive at roughly `920px` and `640px` breakpoints.

## Maintenance Notes

- Preserve the single-page structure unless the user asks for routing or separate pages.
- Keep public-facing Chinese copy consistent across `app/page.tsx`, `app/layout.tsx`, and footer/contact sections.
- Be careful with file encoding. The current terminal output shows mojibake for Chinese text in some TypeScript files; before editing large copy blocks, verify the actual rendered page or inspect the file with an editor that preserves UTF-8.
- If changing brand assets, place project-bound images under `public/assets/` and update references accordingly.
- If modifying the booking form, remember it is currently frontend-only and does not submit to a backend.
