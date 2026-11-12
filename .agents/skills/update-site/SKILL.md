---
name: update-site
description: Update Rickie Reilly's GitHub Pages homepage or interactive SpaceX valuation model, verify behavior, publish requested changes, and recover a prior version.
---

1. Read AGENTS.md and README.md. Confirm the Git remote points to
   `reillz10/rickiereilly.com`. Fetch the latest source and inspect local changes
   before editing; preserve other people's work.
2. Update only what the user requests. The homepage is `docs/index.html`; the
   model is `docs/spacex/index.html`. Use relative links that work both on the
   GitHub address and custom domain. Financial assumption changes need a source
   or an explicit user-provided value.
3. Serve `docs/` locally. Test desktop and mobile in a browser. Check console
   errors, chart rendering, sliders, year controls, reset, and summary copying
   where affected. Changing an input must update the visible outputs and chart.
   Check for horizontal overflow and broken local links. Report any unavailable
   external dependencies. Keep screenshots and scratch artifacts outside docs.
4. Review the diff for unintended changes and secrets. Commit a clear description.
   Use a branch or PR when review is requested. Publish when the user's request
   authorizes publishing; pushing to main deploys automatically. Do not change
   DNS or the Pages domain as a side effect of a content update.
5. Check the Pages build status and fetch the live page. Compare its contents to
   the intended revision and verify affected interactions in the live browser.
   Report the commit, URL, checks, and any blockers; never claim deployment
   success based only on a successful push.
6. To undo an update, revert the relevant commit and publish the revert. Preserve
   history rather than force-pushing or resetting shared branches.

This skill supplies a procedure, not credentials. Future sessions need GitHub
access with repository write permissions. Never put access tokens in the site.
