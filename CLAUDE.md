# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Repository Overview

This is a Zenn content repository for managing technical articles published on Zenn.dev. Articles are written in Markdown and managed through the Zenn CLI tool.

## Primary Use Cases for Claude Code

Claude Code is primarily used for **article content review and quality assurance** in this repository. The main focus areas include:

### Content Review

- **Structural analysis**: Evaluate article organization, logical flow, and section arrangement
- **Readability assessment**: Check clarity, coherence, and accessibility for target audiences
- **Technical accuracy**: Verify technical explanations, code examples, and implementation details
- **Completeness check**: Ensure all necessary information is covered without gaps

### Writing Quality Review

- **Grammar and style**: Review Japanese language quality, consistency in tone and terminology
- **Clarity improvements**: Suggest clearer expressions and better word choices
- **Redundancy detection**: Identify repetitive content or unnecessary verbosity
- **Consistency verification**: Ensure consistent terminology and formatting throughout articles

### Content Enhancement Suggestions

- **Missing information**: Identify gaps in explanations or missing context
- **Example improvements**: Suggest better code examples or real-world use cases
- **Reader perspective**: Evaluate whether content addresses reader needs and questions
- **SEO and discoverability**: Review titles, topics, and content structure for better searchability

### Pre-Publication Checklist

- Verify frontmatter is correctly configured (title, emoji, type, topics, published status)
- Check all code blocks are properly formatted and runnable
- Ensure links and references are valid and accessible
- Confirm the article follows Zenn's content guidelines

**Note**: Claude Code should focus on content quality and structure rather than automated content generation. The goal is to assist with thoughtful review and improvement of human-written articles.

## Technology Stack

- **Package Manager**: pnpm 10.21.0
- **Node.js**: 24.11.0 (managed via mise)
- **CLI Tool**: zenn-cli 0.2.10

## Common Commands

### Preview Content

```bash
pnpm zenn preview
```

Launches a local server to preview articles in the browser before publishing.

### Create New Article

```bash
pnpm zenn new:article
```

Generates a new article file in the `articles/` directory with proper frontmatter.

### List Articles

```bash
pnpm zenn list:articles
```

Displays all articles in the repository.

### Version Check

```bash
pnpm zenn --version
```

## Repository Structure

- `articles/` - Contains individual article files (`.md` format)
- `mise.toml` - Development environment configuration (Node.js and pnpm versions)
- Article files use frontmatter with fields:
  - `title`: Article title
  - `emoji`: Display emoji
  - `type`: Either "tech" (technical) or "idea"
  - `topics`: Array of topic tags
  - `published`: Boolean for publication status

## Content Guidelines

Articles are written in Japanese and follow Zenn's Markdown format. Each article is a standalone `.md` file in the `articles/` directory with a unique slug identifier in the filename.

For detailed Zenn CLI usage, refer to: <https://zenn.dev/zenn/articles/zenn-cli-guide>
