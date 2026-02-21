# Contributing to Zakat Calculator

Thank you for taking the time to contribute. This is a small, focused open-source project and contributions of all sizes are welcome — from typo fixes in the Islamic ruling notes to new currency support.

## Table of Contents

- [Contributing to Zakat Calculator](#contributing-to-zakat-calculator)
  - [Table of Contents](#table-of-contents)
  - [Code of Conduct](#code-of-conduct)
  - [Getting Started](#getting-started)
  - [How to Contribute](#how-to-contribute)
    - [Bug Reports](#bug-reports)
    - [Feature Requests](#feature-requests)
    - [New Currency](#new-currency)
    - [Islamic Ruling Corrections](#islamic-ruling-corrections)
    - [Code Contributions](#code-contributions)
  - [Project Structure](#project-structure)
  - [Style Guidelines](#style-guidelines)
  - [Submitting a Pull Request](#submitting-a-pull-request)

---

## Code of Conduct

By participating, you agree to abide by the [Code of Conduct](CODE_OF_CONDUCT.md). Please read it before contributing.

---

## Getting Started

The entire project is a single self-contained HTML file — `index.html`. There is no build step, no package manager, and no dependencies to install.

```bash
git clone https://github.com/imusmanmalik/zakat-calculator.git
cd zakat-calculator
open index.html   # or double-click, or serve with: python3 -m http.server 8080
```

That's it. Edit `index.html` in any text editor and refresh the browser to see changes.

---

## How to Contribute

### Bug Reports

Use the [bug report issue template](.github/ISSUE_TEMPLATE/bug_report.md). Please include:
- Browser and OS
- Steps to reproduce
- Expected vs. actual behaviour
- A saved JSON file if relevant (strip any real financial data first)

### Feature Requests

Use the [feature request template](.github/ISSUE_TEMPLATE/feature_request.md). Describe the use case, not just the solution.

### New Currency

Use the [currency request template](.github/ISSUE_TEMPLATE/currency_request.md).

### Islamic Ruling Corrections

If you believe a ruling note is inaccurate or incomplete, open an issue citing the scholarly source you are referencing. The project aims to reflect mainstream contemporary positions; scholarly disagreements are noted but the tool cannot adjudicate between schools of thought.

### Code Contributions

Good areas to contribute:

| Area                   | Notes                                                                                        |
| ---------------------- | -------------------------------------------------------------------------------------------- |
| New display currencies | Add to `CURRENCIES`, `BASE_CURRENCIES`, `BASE_CURRENCY_SYMS`, and the `<select>` in the HTML |
| New spot metals        | Add to `RDEFS` and `METALS` arrays                                                           |
| Accessibility          | ARIA labels, keyboard navigation, screen reader support                                      |
| Internationalisation   | RTL layout improvements, translated ruling notes                                             |
| UI/UX polish           | Responsive layout on very small screens                                                      |

---

## Project Structure

```
index.html          ← the entire application (HTML + CSS + JS, all inline)
LICENSE
README.md
CONTRIBUTING.md
CODE_OF_CONDUCT.md
SECURITY.md
.github/
  workflows/
    deploy.yml      ← GitHub Pages auto-deploy
  ISSUE_TEMPLATE/
    bug_report.md
    feature_request.md
    currency_request.md
  PULL_REQUEST_TEMPLATE.md
```

The HTML file is structured in three logical sections separated by comments:

1. **CSS** (`<style>` block) — CSS custom properties (variables) at the top, then component styles
2. **HTML** — static structure, dynamic lists are empty `<div>` containers filled by JS
3. **JavaScript** (`<script>` block) — sections separated by `// ═══` banner comments

---

## Style Guidelines

- **No external dependencies.** Keep the tool self-contained and offline-capable.
- **No build step.** The file must be openable directly in a browser without any tooling.
- **Preserve the existing CSS variable system.** All colours and spacing use `--var` tokens defined in `:root`.
- **Islamic guidance text** should be factual and neutral, not prescriptive. Cite scholarly sources in comments where possible.
- **Privacy:** Do not add any analytics, tracking pixels, or third-party scripts beyond the existing Google Fonts and rate API.

---

## Commit Message Convention

This project uses [Conventional Commits](https://www.conventionalcommits.org/) to drive automated releases via [release-please](https://github.com/googleapis/release-please). Please format your commit messages accordingly:

| Prefix | When to use | Version bump |
|---|---|---|
| `fix:` | Bug fix | Patch (1.0.**1**) |
| `feat:` | New feature or asset class | Minor (1.**1**.0) |
| `feat!:` or `BREAKING CHANGE:` | Breaking change to save format | Major (**2**.0.0) |
| `docs:` | README, CONTRIBUTING, rulings text | No release |
| `chore:` | Maintenance, dependency updates | No release |
| `style:` | CSS / formatting only | No release |
| `refactor:` | Code restructure, no behaviour change | No release |

**Examples:**
```
feat: add Malaysian Ringgit (MYR) support
fix: correct silver nisab calculation when base currency is PKR
docs: improve real estate rental ruling note with scholarly citation
chore: update fallback exchange rates
```

A release-please PR is opened automatically when releasable commits land on `main`. Merging that PR publishes the GitHub Release and attaches `index.html` as a downloadable asset.

---

## Submitting a Pull Request

1. Fork the repository and create a branch from `main`.
2. Make your changes to `index.html` (and docs if relevant).
3. Test in at least one Chromium-based browser and one non-Chromium browser (Firefox or Safari).
4. Open a pull request using the [PR template](.github/PULL_REQUEST_TEMPLATE.md).
5. Describe what changed and why.
6. Use a Conventional Commit-style title on the PR (GitHub squash-merges use the PR title as the commit message).

Pull requests that add tracking, require a build step, or introduce external runtime dependencies will not be merged.
