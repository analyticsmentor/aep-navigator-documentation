# AEP Navigator - Chrome Browser Extension Documentation

## Overview

* **AEP Navigator** is a productivity extension that helps you collect, organize, and launch links to various Adobe Experience Platform (AEP) products and features you frequency visit.
* It detects your current AEP org and sandbox from the active tab, scrapes categorized links, and renders them in a compact popup and a full dashboard.
* It lets you add multiple Adobe orgs and keep them visible as chips, and supports inline icons for links for easier visual scanning.

## Key Features

* **One-click capture** of the active AEP org, sandbox, and related navigation links.
* **Clean popup** with three distinct sections and separate message bars:
  * Header with a button to launch the full dashboard.
  * **Add New Org** section with its own progress and status messages.
  * **Added Orgs** section showing org chips and its own messages such as “No org added yet.”
  * **Quick Links** list that remains unchanged and scrollable.

* **Full dashboard view** with:
  * Centered header title and right-aligned actions.
  * Centered org and sandbox filters with chips.
  * Product columns whose link content is centered for readability.
  * Links displayed as “icon text,” using the AEP page’s inline SVG icon when available.

* **Non-destructive storage** of icons as raw SVG for crisp rendering on any DPI or theme.
* **Lightweight UI theme** with alternating section backgrounds and consistent spacing.

## Supported Environment

* **Chromium-based browsers** with Manifest V3 support:
  * Tested primarily on Chrome.

* **AEP surfaces at:**
  * `https://experience.adobe.com/*
  * Also supports Journey Optimizer, Platform Home, and similar AEP apps under the same host.

---


## Getting Started

After installing the extension from the store:  
1. Open an AEP page in your browser where the URL looks like: `https://experience.adobe.com/#/@yourOrg/...`
2. Click the extension icon to open the popup.
3. Use **“Add org”** in the Add New Org section.
   * The popup shows progress and results in that section’s message bar.
   * If the org already exists, you’ll see an option to reload and refresh links.
4. Once added, your org appears as a chip in the **Added Orgs** section.
5. Click **“Launch Dashboard”** to view the full dashboard with categorized links and filters.

---

## UI Reference

### Popup UI

* **Header:** Brand/title centered in the header; “Open Dashboard” button on the right.
* **Add New Org section:**
  * “Add org” button.
  * Dedicated message area showing detection status, org keys, and progress.

* **Added Orgs section:** * Message area for org-level status (e.g., “No AEP org added yet”).
  * Org chips rendered for each saved org.

* **Quick Links section:** Renders a scrollable list of links aggregated from your org data.

### Dashboard UI

* **Header and actions:** Title centered and three delete buttons aligned to the right. Each button let you delete the selected org, the sandboxaligned or the entire dashboard respectively.
* **Filters:** Org and sandbox filters centered with chips for clarity.
* **Product columns:** * Each product area displays categories and links.




---

## How It Works

* **Detection:** Checks the active tab’s URL to detect AEP presence and infer the org key from the hash segment.
* **Scraping:** The background/content script collects categorized links, reading text, `href`, and extracting the first inline SVG icon.
* **Storage model:** Data persists per browser profile using `chrome.storage`. Orgs are keyed by identifier, holding labels and `quickLinks` objects.
* **Rendering:** Popup shows chips; Dashboard renders full categories with centered "icon text" alignment.

---

## Usage Tips

* If “Add org” button reports “No AEP detected,” ensure you are on an active Adobe Experience Platform tab i.e. Data Collection, RTCDP, CJA or AJO. Other pages from AEP or AEC will not work.
* Use **“Reload Org”** when AEP navigation has changed to refresh links and icons.
* Links without icons will still render correctly with aligned text.


---

## Privacy and Security

* **Local Storage:** All data is stored locally in `chrome.storage`.
* **No External Tracking:** Absolutely no data is sent to any external servers or third parties.
* **Scoped Access:** Scripts only run on specified Adobe domains.

---

## FAQ

* **Can I export my links?** Not built-in yet, but data can be serialized from `chrome.storage`.
* **Does it support multiple sandboxes?** Yes, sandboxes are reflected in captured links.
* **Does it support multiple Organizations?** Yes, organizations are being shown as chips.
* **Will it work outside experience.adobe.com?** No, scraping is limited to that host for safety.

---

## Privacy Policy:

> We do not collect, track, transmit, sell, or share any personal data. All processing happens locally in your browser. The extension only reads AEP pages you open to extract navigation links and optional inline icons.

**Contact:** For questions, contact the maintainer at `rajdeep91@outlook.com`.

