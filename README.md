# GSCBuddy

GSCBuddy is a Chrome Extension designed to simplify and automate Google Search Console (GSC) workflows, such as extracting sitemap URLs, identifying untracked sub-properties, and bulk-creating properties via the official Google Webmasters API.

---

## Features

- **Automated Sitemap Parsing:** Instantly scan any XML sitemap and identify parent paths that should be tracked as distinct properties.
- **Bulk Property Creation (API):** Provision dozens of properties in GSC with a single click using a secure, native Chrome OAuth integration.
- **Index Coverage Extraction:** Automate navigation through GSC index coverage reports to extract granular indexing data.
- **CSV Export:** Easily export initial URLs and scraped data for further analysis.
- **Premium UI Theme:** A clean, responsive interface that respects your system's dark/light mode preference.
- **Background Operations:** Scraping tasks run in minimized windows to avoid interrupting your primary workflow.

---

## Installation

1. Clone or download this repository.
2. Open Chrome and navigate to `chrome://extensions/`.
3. Enable **Developer mode** in the top right corner.
4. Click **Load unpacked** and select the directory containing the extension files (where `manifest.json` is located).

## Configuration (For API Features)

To use the Bulk Property Creation API feature, you must configure an OAuth Client ID:
1. Create a project in the [Google Cloud Console](https://console.cloud.google.com/).
2. Enable the **Google Search Console API**.
3. Create OAuth 2.0 credentials for a **Chrome App/Extension** using the extension's ID.
4. Update the `"oauth2"` section in `manifest.json` with your generated `client_id`.

---

## Conventions & Contribution

- **One feature, one branch.** Keep work atomic.
- **Code separation:** UI logic is separated from background state and script execution.
- **`main` is always runnable.** WIP lives on branches.
