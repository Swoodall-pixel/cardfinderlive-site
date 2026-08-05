# Website Docs

Status: canonical website documentation
Last updated: 2026-08-04

## Purpose

This folder is the canonical documentation home for the CardFinder Live public website.

Use these files to understand the live site, its copy, its routing, and how to deploy future edits safely.

## Canonical files

- `WEBSITE_DEPLOYMENT.md` — production repository, branch, GitHub Pages workflow, checklist, rollback guidance, and recovery tags
- `FOUNDER_STORY.md` — canonical founder-story source content
- `OUR_STORY_PAGE_SPEC.md` — canonical implementation spec for the Our Story page
- `WEBSITE_V2_ROADMAP.md` — post-launch website ideas only

## Current website status

- Launch V1 is complete
- the homepage remains product-first
- Our Story is live
- privacy, terms, and support use directory-based routing
- the site is intended to stay simple, credible, and collector-first

## Deployment reference

Start here for future website releases:

- `WEBSITE_DEPLOYMENT.md`

## Quick AI navigation

When a future ChatGPT or Codex session needs to work on the website, read these docs in order:

1. `README.md`
2. `WEBSITE_DEPLOYMENT.md`
3. `FOUNDER_STORY.md`
4. `OUR_STORY_PAGE_SPEC.md`
5. `WEBSITE_V2_ROADMAP.md`

If the task is only to edit copy or routes, follow the required website workflow in `WEBSITE_DEPLOYMENT.md` and do not call the task complete until:

- the changes are committed
- the changes are pushed to `main`
- `origin/main` matches `HEAD`
- GitHub Pages has started deploying the new commit
- the live page matches the newest commit

Use the mandatory reporting checklist from `WEBSITE_DEPLOYMENT.md` for every website task.

## Notes

- Do not treat `WEBSITE_V2_ROADMAP.md` as Launch V1 scope
- Do not use old `/privacy.html`, `/terms.html`, or `/support.html` assumptions for production navigation
- Keep internal links aligned with the route-based live site
