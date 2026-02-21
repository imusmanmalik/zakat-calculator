# Security Policy

## Scope

This project is a **static, browser-only HTML file**. It has no server component, no database, no authentication, and no backend. All computation happens locally in the user's browser.

The primary security surface is:

| Surface                             | Notes                                                                                                                                          |
| ----------------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------- |
| Third-party CDN (exchange rate API) | Data fetched from `cdn.jsdelivr.net` and `latest.currency-api.pages.dev`. Only numeric rate values are used; no script execution from the API. |
| Google Fonts CDN                    | CSS/fonts only. Can be self-hosted by copying font files locally if preferred.                                                                 |
| JSON load/save                      | User loads their own locally-saved JSON files. The loader parses JSON from the file — not `eval`.                                              |
| `localStorage` / cookies            | Not used. No data is persisted by the app itself (only the file the user explicitly saves).                                                    |

## Reporting a Vulnerability

If you discover a security issue (e.g., XSS in the JSON loader, malicious content injection via rate API data, etc.), **please do not open a public GitHub issue**.

Instead, report it via [GitHub's private vulnerability reporting](https://github.com/imusmanmalik/zakat-calculator/security/advisories/new) or send a direct message to the maintainer on GitHub (`@imusmanmalik`).

Please include:

- A description of the vulnerability
- Steps to reproduce
- Potential impact
- A suggested fix if you have one

You will receive a response within 7 days. If the issue is confirmed, a fix will be released as promptly as possible and you will be credited in the release notes (unless you prefer to remain anonymous).

## Supported Versions

Only the latest version on the `main` branch is actively maintained.
