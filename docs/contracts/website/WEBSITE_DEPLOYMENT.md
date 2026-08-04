# Website Deployment

Status: canonical deployment reference
Last updated: 2026-08-04

## Purpose

This document is the canonical guide for publishing the CardFinder Live public website.

Use this document when editing, reviewing, committing, pushing, or rolling back the production site.

## Production repository

- Repository: `Swoodall-pixel/cardfinderlive-site`
- Production branch: `main`
- Local repository path: `/Users/stevenwoodall/LocalDev/cardfinderlive-site`
- Hosting platform: GitHub Pages
- Production domain: `https://cardfinderlive.com`

## Canonical website references

- `docs/contracts/website/README.md`
- `docs/contracts/website/FOUNDER_STORY.md`
- `docs/contracts/website/OUR_STORY_PAGE_SPEC.md`
- `docs/contracts/website/WEBSITE_V2_ROADMAP.md`

## GitHub Pages deployment flow

1. Make website edits in the website repository.
2. Verify the work in the local repo.
3. Review the diff carefully.
4. Commit on `main`.
5. Push `main` to `origin`.
6. Allow GitHub Pages to deploy automatically.
7. Verify the live site after the deployment finishes.

GitHub Pages is the production host for the public website. No separate build pipeline is required for Launch V1.

## Deployment checklist

Before committing:

- [ ] Confirm the intended homepage / route changes are present locally.
- [ ] Confirm the Our Story, Privacy, Terms, and Support routes still work locally.
- [ ] Confirm no unrelated files changed.

Before pushing:

- [ ] Review `git status`.
- [ ] Review `git diff`.
- [ ] Confirm the commit contains only approved website changes.

After pushing:

- [ ] Confirm the branch is `main`.
- [ ] Confirm the push succeeded.
- [ ] Confirm GitHub Pages has begun deploying the new commit.
- [ ] Check the live site after propagation.

## Verification checklist

Verify these URLs:

- `https://cardfinderlive.com/`
- `https://cardfinderlive.com/our-story/`
- `https://cardfinderlive.com/privacy/`
- `https://cardfinderlive.com/terms/`
- `https://cardfinderlive.com/support/`

Verify that the live site matches the expected committed state.

If the live site still shows older content:

- confirm the latest commit was pushed to `main`
- confirm GitHub Pages is serving from the correct branch
- confirm the repo has no unpublished working-tree edits
- confirm the browser is not showing a cached local copy

## Rollback / recovery guidance

If a website release needs to be undone:

1. Identify the last known-good commit.
2. Create a new commit that reverts the bad website change.
3. Push the revert commit to `main`.
4. Allow GitHub Pages to redeploy.

Do not force-push production history unless you are intentionally rewriting release history for a documented reason.

## Green-tag convention

Use a lightweight recovery tag for notable website releases:

- `green-website-launch-v1`

Tag conventions:

- tags should point at the exact commit that was verified as production-ready
- tags are recovery anchors, not release history replacements
- create the tag only after the commit has been verified locally

## Common mistakes

- editing files locally and assuming GitHub Pages already has them
- forgetting to commit before pushing
- pushing to the wrong branch
- changing route folders without updating internal links
- forgetting that GitHub Pages deploys asynchronously after push
- confusing local file changes with production state
- mistaking `/privacy.html` style routing for the current directory-based routes

## Future website editing workflow

For future website changes:

1. Read this document first.
2. Review the current website docs in `docs/contracts/website/`.
3. Make the smallest possible content or routing change.
4. Verify the local site.
5. Commit on `main`.
6. Push to `origin/main`.
7. Wait for GitHub Pages deployment.
8. Re-verify production.

## Lesson learned

Before considering a website task complete, always verify:

- `git status` is clean
- the changes are committed
- the changes are pushed to `main`
- the live website matches the latest production commit

## Canonical source of truth

For launch V1 and beyond, the website repository itself is the source of truth for the public site.

The docs in `docs/contracts/website/` should always describe the live site as it actually exists.
