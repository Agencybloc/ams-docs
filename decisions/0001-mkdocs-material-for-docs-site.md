# ADR 0001: MkDocs Material as docs site renderer

**Date:** 2026-04-27  
**Status:** Accepted

## Context

We needed a Markdown-first static site generator that a non-engineer audience can read without special tooling, that deploys cheaply to GitHub Pages, and that the AI pipeline can write to without learning a complex CMS.

## Decision

Use [MkDocs Material](https://squidfunk.github.io/mkdocs-material/). Rendered HTML deployed to GitHub Pages via GitHub Actions.

## Rationale

- Markdown source — the AI pipeline writes Markdown; no adapter layer needed.
- Material theme — clean, searchable, mobile-friendly out of the box.
- Mermaid support — diagram-as-code without external tooling.
- GitHub Pages deployment — free, static, no runtime to operate.
- Admonition support — structured callouts for warnings and tips that match the style guide.

## Consequences

- Docs are static; no server-side search (MkDocs ships client-side search, sufficient for this audience).
- Hosting on GitHub Pages means the `ams-docs` repo must be on GitHub (already true — code repos may still be on Bitbucket during the transition).
- If the site grows beyond ~5,000 pages, build time may increase; budget a CI cache for the `site/` artifact.
