# Repository Guidelines

## Agent Usage: Codex

Codex is primarily a writing-quality partner. Ask it to outline articles, tighten narrative flow, and double-check that the content matches the stated intent before publishing. When drafting, provide Codex with the article goal, target audience, and any must-include references so it can suggest coherent structure, heading hierarchy, and callouts. When reviewing, have Codex compare the manuscript against Zenn conventions (front matter, emoji, topics, published flag) and flag unclear logic, missing context, or inconsistent terminology. Codex may recommend rewrites, reordering, or supplemental examples, but it should not be used for implementing automation, editing multimedia assets, or making repository-wide tooling changes. Treat Codex as the final editorial pass: after local previewing, share the near-final Markdown so it can spot regressions, ensure tone consistency, and confirm cross-links or citations resolve correctly.

## Project Structure & Module Organization

Source content lives under `articles/` for standalone posts and `books/` for multi-chapter series; keep media assets alongside each article or chapter folder so previews stay portable. `mise.toml` pins Node.js 24.11.0 and pnpm 10.21.0, while `package.json` only tracks `zenn-cli`, so add other dependencies sparingly and justify them in pull requests.

## Build, Test, and Development Commands

Run `pnpm install` once per toolchain bump to sync lockfiles. Draft new material with `pnpm dlx zenn new:article --slug my-topic` or `... new:book --slug ref-guide` to scaffold correctly named directories. Use `pnpm dlx zenn preview` for a live Markdown preview on <http://localhost:8000>, and rerun `pnpm dlx zenn build` before publishing to ensure Zenn-specific checks pass.

## Coding Style & Naming Conventions

Write Markdown in UTF-8 with front-matter the Zenn CLI expects (`title`, `emoji`, `type`, `topics`, `published`). Prefer lowercase-kebab slugs that match filenames, and keep headings sentence case for readability on zenn.dev. Use fenced code blocks with language tags, two-space indentation inside lists, and keep line length under ~100 characters to avoid Zenn wrap issues. Follow any formatter settings shipped with your editor; no repo-wide formatter is enforced yet.

## Testing Guidelines

There is no automated test suite today; when contributing scripts or custom tooling, add lightweight checks under a future `tests/` directory and wire them into `pnpm test`. Until then, manually open the Zenn preview in at least one evergreen browser, verify internal links, and confirm metadata renders as expected before opening a pull request.

## Commit & Pull Request Guidelines

Recent history shows short, purposeful commit messages in Japanese (e.g., “pnpmのアップグレード”). Continue that style: summarize the change in one clause, present tense, and focus on user-visible impact. For pull requests, include: a short narrative of the change, screenshots or preview links for visual updates, reproduction steps for bug fixes, and references to Zenn articles/issues if applicable. Request review once `pnpm install`, `pnpm dlx zenn preview`, and (when available) `pnpm test` all succeed locally.

## Content Workflow Tips

Store drafts with `published: false` until ready; the Zenn CLI hides them from production deploys but keeps them previewable. Use topic tags that already exist on zenn.dev to improve discovery, and add cross-links between related `articles/` and `books/` entries to share authority. Commit both Markdown and any supporting diagrams so future contributors can iterate without guessing context.
