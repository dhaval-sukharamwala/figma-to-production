# Figma → Production

**Change one design token. Watch every app update.**

An interactive demo of a design-token pipeline: a value edited in Figma travels through export, review, CI, and build, and lands in a web dashboard and a native mobile screen — without an engineer touching a UI file.

🔗 **[Live demo](https://dhaval-sukharamwala.github.io/figma-to-production/)**

---

## What this is

A design token is a named value stored once — `color/primary`, `space/md`, `radius/md` — and referenced everywhere instead of being retyped per platform. This page makes that idea tangible by letting you edit tokens and watch the consequences propagate through a simulated end-to-end pipeline.

It's a portfolio piece about a **product decision**, not a build tool: where should consistency live? The argument is that it belongs in the build rather than in documentation and memory.

## What it demonstrates

The page is a seven-part scroll narrative:

| # | Section | What happens |
|---|---------|--------------|
| 1 | **Token** | Seven editable variables from a Figma collection (`color/primary`, `color/surface`, `color/text`, `elevation/md`, `radius/md`, `space/md`, `type/size-body`) with light and dark modes, plus a live contrast check. |
| 2 | **Pipeline** | Figma export → `tokens.json` → git commit → GitHub Action → Style Dictionary → Vercel deploy → mobile bundle. Delays are deliberate, so the timing reads as real. |
| 3 | **Code** | The build output in three platform-native forms: `tokens.css` (hex), `Tokens.swift` (normalised floats), `tokens.xml` (dp). Nobody converted anything by hand. |
| 4 | **Apps** | A React web dashboard and an iOS/Android screen, both re-rendered from the files the build just wrote. Different layouts, identical values. |
| 5 | **Numbers** | What one publish moved: 276 tokens, 8 platforms, 2 themes. |
| 6 | **Why** | The same spacing change handled two ways — two days and four chances to mistype, versus one review. |
| 7 | **Outcome** | The business goal, the decision, and what it buys: one review instead of one sweep per platform, no accumulating visual drift, dark mode as a value swap, contrast checked at build time. |

## Scope and honesty

The pipeline is **simulated**. There is no live Figma file, no real CI run, and no deploy behind the buttons — the timings are modelled to match what the real steps cost.

The demo is also explicit that tokens remove **manual retyping, not deployment latency**. Web picks up a change on the next deploy; mobile picks it up on the next app release. That constraint is part of the point, not a gap in the demo.

## Tech

Static site, deployed on GitHub Pages. No build step required to view it — open the page and scroll.

> Adjust this section to match the actual stack (framework, bundler, dependencies) before publishing.

## Running locally

```bash
git clone https://github.com/dhaval-sukharamwala/figma-to-production.git
cd figma-to-production

# any static server works
python3 -m http.server 8000
# or
npx serve .
```

Then open `http://localhost:8000`.

## Deployment

Published via GitHub Pages from this repository. Pushing to the deployment branch updates the live site.

## Author

**Dhaval Sukharamwala**
[Email](mailto:dhavaldvl00@gmail.com) · [LinkedIn](https://www.linkedin.com/in/dhaval-sukharamwala/)

Design systems · design tokens · web, iOS, Android · accessibility

---

© 2026 Dhaval Sukharamwala
