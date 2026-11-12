---
name: premium-website-polish
description: Use when building, reviewing, or iterating on a client marketing website (desktop and mobile), when a site "feels like a template", "AI-generated", "clustered", "grid-like on mobile", or "not premium", when applying client or audit feedback to a new version, or before deploying a website build for client review.
---

# Premium Website Polish

## Overview
A site with good content still reads as "a good website, not a premium experience" when sections repeat one layout, mobile is a stacked list, motion is missing, and details (icons, type, CTAs, footer, scroll) are inconsistent. This skill is the pass that turns a working site into one a client approves. Every rule below came from a real client correction round.

**Core principle:** the visitor should *feel* quality before reading about it, and nothing you add may break what already feels good (scroll smoothness, agreed decisions).

## 1. Decisions before design
- Keep a decision log (client calls, chat agreements, rejected items). Check every suggestion — yours, a ChatGPT/AI audit, a teammate's — against it. Drop audit items that contradict agreed decisions; list them as rejected with the reason.
- Never reintroduce something the client already rejected (e.g. a colour treatment they moved away from).
- Content awaiting client confirmation: hide behind a flag (default off), don't delete. Anything *you* chose on the client's behalf (image picks, wording) goes on an explicit "needs client confirmation" list.
- New feedback round → new version/branch from the most stable base. Never mutate a released version.

## 2. Layout rhythm (the "AI-generated feel" killer)
- No two adjacent sections share a layout. Before finishing, list sections top-to-bottom with their layout type; any repeat → redesign one.
- Mobile is designed, not collapsed. No horizontal swipe rows; also no "everything becomes a list/grid". Give each section its own treatment: stacking cards, zig-zag, timeline, offset quotes, full-bleed lead image, editorial figures.
- Clear section separation on mobile (spacing, background shifts, dividers). If it feels "clustered", group the content (e.g. a long city list → labelled groups: Domestic / International).
- When asked for a creative pass: build it, don't ask questions first.

## 3. Visual details
| Area | Rule |
|---|---|
| Typography | One type scale. Audit label/heading/body sizes across all pages. Page headers identical in style on every page. |
| Icons | Each icon must mean its content. One family, one stroke weight, one size per context. |
| Numbers | Stats count up on reveal. Never show small quantities as progress bars — a short bar reads as "not enough". Use editorial figures. |
| Diagrams | A layperson must understand it with no legend. Label directly on the drawing, no numbered keys. If it still needs explaining → use a premium real photo instead. |
| Text over images | Decorative images behind text at very low opacity (~0.04), no hover state that reduces legibility. |
| Brand colour | Use gradients and light washes, not big solid brand-colour slabs, unless the client asked for that. |
| Footer | Columns, socials, divider, legal row. Premium and quiet, not a solid colour block. |
| CTA bands | Visibly separated from footer (background + size). On phones buttons go full-width and stack. Check **every** page's CTA, not just Home. |
| Mobile menu | Same polish and header consistency as desktop. |

## 4. Motion and scroll
- Section reveals, word-by-word heading reveal, list stagger. Respect `prefers-reduced-motion`.
- **Never hijack native scroll** (snap, stepper, speed gates, wheel interception) on a scroll-driven section. It breaks smoothness site-wide. To slow down a scroll story, add scroll length/hold per stop instead.
- Logo and Home nav scroll to the true top of the page, including when you come from another page.
- Scroll feel can't be checked headless. Preview on a LAN URL and let the user try it on a trackpad and phone *before* deploying.

## 5. Performance and assets
- Check every image for pixelation at its rendered size × DPR. Serve AVIF/WebP at 480/800/1200 with `srcset`.
- Heavy 3D/WebGL: poster first, prewarm shaders in yielded chunks, move geometry work to a Web Worker, hold heavy images until the 3D is ready. Test on throttled slow 4G and a mid-range phone.
- In-page feedback widgets must work on phone taps, not just desktop clicks.

## 6. Release discipline
- Run the project's checks (typecheck, lint, tests, build), then screenshot at 1440 / 1024 / 390 / 320.
- Commit and deploy only when the user says so. After deploying, check the live URL.

## Red flags — stop and fix
- "The mobile version just stacks the desktop sections"
- Two sections in a row look the same
- "The audit said so" when it conflicts with a client decision
- Adding scroll control to make an animation "not get skipped"
- A diagram that needs a legend
- A bar chart of small numbers
- "Looks fine in the headless screenshot" as proof of scroll feel
