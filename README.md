# GitHub PR Attention - TRMNL Recipe

A [TRMNL](https://usetrmnl.com) recipe that shows pull requests needing your attention in a specific GitHub repository. It displays PRs that either:

1. **Have a specific label** (e.g., `ready-to-merge`)
2. **Request your review**

PRs matching both criteria are shown once with both indicators.

Forked from [GitHub Pull Requests](https://github.com/GuilhermeMorais/trmnl-github-pull-requests) by Guilherme Morais.

## How It Works

The recipe uses TRMNL's built-in polling strategy to make a single GraphQL request to GitHub with **two aliased searches**:

- `labeled`: `is:pr is:open repo:{owner}/{repo} label:{label}`
- `review_requested`: `is:pr is:open repo:{owner}/{repo} review-requested:{username}`

Results are merged and deduplicated in Liquid. Each PR shows:

- Review status icon (approved, changes requested, commented, pending, review required)
- PR title and number
- Reason tags: label badge and/or reviewer badge
- Comment count and latest review timestamp

## Custom Fields

| Field | Description |
|-------|-------------|
| **GitHub API Token** | [Personal Access Token](https://github.com/settings/personal-access-tokens) with read access to Pull Requests |
| **GitHub Username** | Your GitHub username (used to find PRs requesting your review) |
| **Repository Owner** | Owner or organization (e.g., `oku-trade`) |
| **Repository Name** | Repository name (e.g., `trade`) |
| **Label** | Label to filter by (e.g., `ready-to-merge`) |

## Local Development

1. Install [trmnlp](https://github.com/usetrmnl/trmnlp)
2. Copy `.trmnlp.yml` and set your `GITHUB_API_TOKEN` env var
3. Update `username`, `repo_owner`, `repo_name`, and `label` in `.trmnlp.yml`
4. Run `trmnlp dev`

## Layouts

- **Full** - Shows title, reason tags, reviewer, comments, and review timestamp
- **Half Horizontal** - Compact version with title, reason tags, and reviewer
- **Half Vertical** - Title, reason tags, comments, and timestamp
- **Quadrant** - Minimal: title, icon indicators, and comment count
