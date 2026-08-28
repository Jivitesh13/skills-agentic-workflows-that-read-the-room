---
name: update-github-info
description: Draft website updates for Mona's GitHub Info site from official GitHub sources.
on:
  workflow_dispatch:
  schedule:
    - cron: '17 9 * * *'
tools:
  edit:
  web-fetch:
safe-outputs:
  create-pull-request:
    title-prefix: "[mona] "
    draft: true
    fallback-as-issue: false
network:
  allowed:
    - github.com
    - github.blog
    - awesome-copilot.github.com
---

# Update Mona's GitHub Info website

Read `notes/mona-notes.md` before drafting changes, so the update reflects Mona's goals and the site's intended audience.

Use official public guidance as the source of truth:
- GitHub Blog: https://github.blog/latest/
- GitHub Changelog: https://github.blog/changelog/
- Awesome Copilot workflows: https://awesome-copilot.github.com/workflows/
- Read external public guidance with web-fetch before writing any summary or recommendation.
- Read repository guidance or reference files with GitHub repository API tools instead of terminal, CLI, or sandboxed commands.

Update `site/content/github-info.md` with concise, practical improvements based on the GitHub Blog, the GitHub Changelog, the Awesome Copilot workflows, and Mona's notes. Keep the wording clear and useful for readers who want a current, accurate overview of GitHub's latest updates and changes.

Web fetch https://awesome-copilot.github.com/workflows/ as part of the review process, and incorporate any relevant workflow ideas into the update while keeping the existing sources and GitHub Blog access intact.

Open a pull request for Mona to review. Use `safe-outputs` with `create-pull-request` so the agent can propose the update without writing directly to `main`. The pull request should be clearly labeled for Mona and should mention the GitHub Info website.
