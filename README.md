<h1 align="center">AEP Navigator</h1>
<p align="center">Bookmark & organize all your AEP Orgs, Sandboxes, and launch links to RTCDP, CJA, AJO, etc.</p>
<h3 align="center">🙋‍♂️ Made by <a href="https://www.linkedin.com/in/rajd33p/">@raj</a></h3>
<p align="center">
  <a href='https://buymeacoffee.com/rajdsingh' target='_blank'>
    <img height='36' style='border:0px;height:36px;' src='https://bmc-cdn.nyc3.digitaloceanspaces.com/BMC-button-images/custom_images/orange_img.png' border='0' alt='Buy Me a Coffee' />
  </a>
</p>
<hr />

# AEP Navigator - Chrome Browser Extension Documentation

## Overview:

* AEP Navigator is a powerful productivity extension designed to streamline your workflow by effortlessly collecting, organizing, and launching links across a wide range of Adobe Experience Platform (AEP) services—such as CDP, CJA, AJO, and Data Collection.
* It intelligently identifies your active AEP organization and sandbox directly from your current browser tab, automatically gathering categorized links and presenting them in a sleek, compact popup as well as a comprehensive dashboard.
* Manage multiple Adobe organizations and sandboxes with ease, enabling seamless switching between environments without any hassle.
* Visual clarity is enhanced by displaying organizations and sandboxes as distinct chips, allowing for quick scanning, while all related links are neatly arranged in organized columns for maximum efficiency.

## Key Features:

* **One-click capture** of the active AEP org, all the sandboxes, and the related navigation links.
* **A clean popup** for the quick links.
* **Full dashboard view** with:
  * All the Orgs and Sandbox filters with chips.
  * All AEP services links are organized in columns.
  * Links displayed as “icon text,” using the AEP page themes and icons.

## Supported Environment

* **Chromium-based browsers** with Manifest V3 support:
  * Tested primarily on Chrome.

* **AEP surfaces at:**
  * `https://experience.adobe.com/*
  * Also supports Journey Optimizer, CDP home page, Data Collection and similar AEP apps under the same host.

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

### Popup UI:

* **Header:** Brand/title centered in the header; “Launch Dashboard” button on the right.
* **Add New Org section:**
  * “Add org” button.
  * Dedicated message area showing detection status, org keys, and progress.

* **Added Orgs section:** * Message area for org-level status (e.g., “No AEP org added yet”).
  * Org chips rendered for each saved org.

* **Quick Links section:** Renders a scrollable list of links aggregated from your org data.

### Dashboard UI:

* **Header and actions:** Title centered and three delete buttons aligned to the right. Each button let you delete the selected org, the sandbox or the entire dashboard respectively.
* **Filters:** Org and sandbox filters centered with chips for clarity.
* **Product columns:** * Each AEP service area displays categories and links.



---

## How It Works:

* **Detection:** Checks the active tab’s URL to detect AEP presence and infer the org key from the hash segment.
* **Scraping:** The background/content script collects categorized links, reading text, `href`, and extracting the first inline SVG icon.
* **Storage model:** Data persists per browser profile using `chrome.storage`. Orgs are keyed by identifier, holding labels and `quickLinks` objects.
* **Rendering:** Popup shows chips; Dashboard renders full categories with centered "icon text" alignment.

---

## Usage Tips:

* If “Add org” button reports “No AEP detected,” ensure you are on an active Adobe Experience Platform tab i.e. Data Collection, RTCDP, CJA or AJO. Other pages from AEP or AEC will not work.
* Use **“Reload Org”** when AEP navigation has changed to refresh links and icons.
* Links without icons will still render correctly with aligned text.


---

## Privacy and Security:

* **Local Storage:** All data is stored locally in `chrome.storage`.
* **No External Tracking:** Absolutely no data is sent to any external servers or third parties.
* **Scoped Access:** Scripts only run on specified Adobe domains.

---

## FAQ:

* **Can I export my links?** Not built-in yet, but data can be serialized from `chrome.storage`.
* **Does it support multiple sandboxes?** Yes, sandboxes are reflected in captured links.
* **Does it support multiple Organizations?** Yes, organizations are being shown as chips.
* **Will it work outside experience.adobe.com?** No, scraping is limited to that host for safety.

---

## Privacy Policy:

> We do not collect, track, transmit, sell, or share any personal data. All processing happens locally in your browser. The extension only reads AEP pages you open to extract navigation links and optional inline icons.

**Contact:** For questions, contact the maintainer at `rajdeep91@outlook.com`.

