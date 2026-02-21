# Zakat Calculator — حساب الزكاة

[![License](https://img.shields.io/badge/license-Apache%202.0-blue.svg)](LICENSE)
[![GitHub Pages](https://img.shields.io/badge/live%20demo-GitHub%20Pages-brightgreen)](https://imusmanmalik.github.io/zakat-calculator/)
[![Last Commit](https://img.shields.io/github/last-commit/imusmanmalik/zakat-calculator)](https://github.com/imusmanmalik/zakat-calculator/commits/main)

A free, open-source, browser-only Zakat calculator with live exchange rates, multi-currency support, and detailed Islamic rulings for every asset class.

**[Try it live →](https://imusmanmalik.github.io/zakat-calculator/)**

> **Privacy first:** Your data never leaves your device. The calculator runs entirely in your browser — no server, no tracking, no account required.

---

## Features

- **Live exchange rates & spot prices** — fetched automatically on page load from a free public CDN API (no API key required). Falls back gracefully if the network is unavailable.
- **Multi-currency inputs** — enter each asset in its original currency (EUR, USD, GBP, CHF, PKR, SAR, AED, CAD, TRY, INR, BDT, QAR); all totals are displayed in your chosen display currency.
- **Precious metals** — Gold, Silver, Platinum, Palladium, and Copper, priced at live spot in grams. Includes notes on the Copper nisab edge case.
- **Silver nisab threshold** — uses the lower silver nisab (595 g) as the primary standard to maximise benefit to Zakat recipients; gold nisab (85 g) shown as reference.
- **Joint accounts** — toggle joint ownership on any bank/cash row and enter your percentage; only your share is counted.
- **Real estate guidance** — interactive ruling engine covering rental property, resale/trading stock, under-construction, personal residence, and mixed intent — with cited Islamic jurisprudence rationale for each.
- **Investments & crypto** — simplified portfolio method (total current market value at 2.5%); includes stablecoin guidance.
- **Liabilities deduction** — deduct currently-due obligations only; includes guidance on mortgage instalment treatment.
- **Hawl date picker** — set your snapshot date for the wealth valuation.
- **Save & load JSON** — export your full calculation to a local JSON file (including a rate snapshot); reload it any time, then refresh rates if needed.
- **Printable summary** — copy a plain-text summary to the clipboard for your records or a scholar review.
- **Zero dependencies** — a single self-contained HTML file. No npm, no build step, no frameworks.

---

## Live Demo

**[https://imusmanmalik.github.io/zakat-calculator/](https://imusmanmalik.github.io/zakat-calculator/)**

---

## Self-Hosting

Because the entire calculator is a single HTML file with no build step or server requirements, self-hosting is trivial:

```bash
# Option 1 — just open the file
git clone https://github.com/imusmanmalik/zakat-calculator.git
open zakat-calculator/index.html   # or double-click it in your file manager

# Option 2 — serve locally (any static server works)
cd zakat-calculator
python3 -m http.server 8080
# then open http://localhost:8080
```

To embed it in an existing project, copy `index.html` to your web server's public directory and it works immediately.

---

## Islamic Disclaimer

> This calculator is an **educational and organisational tool**. It is not a fatwa, a scholarly ruling, or a substitute for consulting a qualified Islamic scholar.
>
> Exchange rates and spot prices are fetched from a free public API and are **indicative only**. For an official Zakat calculation, verify rates against a source you consider authoritative (your central bank, a trusted gold dealer, or your local Islamic finance authority).
>
> The rulings shown for each asset class are based on the positions of mainstream contemporary scholars, but scholarly opinion differs on several points (particularly real estate, crypto, and investment portfolios). If in doubt, consult a scholar.

---

## Supported Currencies

| Currency        | Code | Currency         | Code |
| --------------- | ---- | ---------------- | ---- |
| Euro            | EUR  | Saudi Riyal      | SAR  |
| US Dollar       | USD  | UAE Dirham       | AED  |
| Pound Sterling  | GBP  | Pakistani Rupee  | PKR  |
| Swiss Franc     | CHF  | Indian Rupee     | INR  |
| Canadian Dollar | CAD  | Bangladeshi Taka | BDT  |
| Qatari Riyal    | QAR  | Turkish Lira     | TRY  |

Spot prices: XAU (Gold), XAG (Silver), XPT (Platinum), XPD (Palladium), XCU (Copper, manual).

---

## Rate Source

Exchange rates and precious metal spot prices are fetched from the [fawazahmed0/currency-api](https://github.com/fawazahmed0/exchange-api) — a free, open, no-key-required CDN-backed currency API. The calculator tries two CDN endpoints and falls back to hardcoded reference rates if both are unreachable.

Rates are considered indicative only. See the disclaimer above.

---

## Contributing

Contributions are welcome. See [CONTRIBUTING.md](CONTRIBUTING.md) for guidelines.

Some good first contributions:

- Add a missing currency to the display currency selector
- Improve the Islamic ruling notes with cited sources
- Translate the UI into another language
- Accessibility improvements

---

## Reporting Issues

- **Bug:** use the [Bug Report](.github/ISSUE_TEMPLATE/bug_report.md) template
- **Feature request:** use the [Feature Request](.github/ISSUE_TEMPLATE/feature_request.md) template
- **New currency:** use the [Currency Request](.github/ISSUE_TEMPLATE/currency_request.md) template
- **Security issue:** see [SECURITY.md](SECURITY.md) — do not open a public issue

---

## License

Apache 2.0 — see [LICENSE](LICENSE).

You are free to use, modify, fork, and redistribute this project, including commercially, as long as you retain the license notice. See the license file for full terms.

---

## Acknowledgements

- [fawazahmed0/exchange-api](https://github.com/fawazahmed0/exchange-api) — free currency & metals API
- [Google Fonts](https://fonts.google.com/) — Playfair Display, Amiri, DM Mono, Lato
- All the scholars whose published rulings on contemporary Zakat questions informed the guidance text in this tool
