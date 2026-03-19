# 🔌 Komfy Bridge — Chrome Extension

> Connect Komfy Studio with AI platforms (Google Flow, etc.) to generate AI videos directly in Workflow Builder — no API key required.

## Table of Contents

- [Overview](#overview)
- [Installation](#installation)
- [Usage](#usage)
- [Updates](#updates)
- [Troubleshooting](#troubleshooting)
- [System Requirements](#system-requirements)

---

## Overview

**Komfy Bridge** is a Chrome Extension that allows Komfy Studio to communicate with external AI platforms. Currently supported:

| Platform | Feature | Model |
|----------|---------|-------|
| Google Flow | AI Video Generation | Veo 3.1 |

The extension acts as a bridge between Komfy Studio and Chrome browser, automatically syncing session tokens and project IDs to perform AI tasks directly from Workflow Builder.

---

## Installation

From version v0.1.39 onwards, the extension is fully managed by Komfy Studio:

1. Open **Komfy Studio** → **Settings** → **Extension** tab
2. The extension will automatically download and install on startup
3. If not installed, click **Install Now**
4. Copy the extension path displayed in the interface
5. Open Chrome → `chrome://extensions` → enable **Developer mode** → **Load unpacked** → paste the path

> 💡 **Tip**: The extension auto-updates when Komfy Studio starts. You only need to reload the extension in Chrome after a new version is available.

---

## Usage

### Connecting to Google Flow

1. Open **Komfy Studio** (must be running first)
2. Open Chrome → go to <a href="https://labs.google/fx/tools/flow" target="_blank">Google Flow</a>
3. Sign in with a Google account that has Veo access
4. Extension icon turns green → connection successful
5. Verify in **Settings** → **Extension** → status shows **Connected**

### Using in Workflow Builder

1. Open the **Workflows** tab in Komfy Studio
2. Add a **Veo 3.1** node to the canvas
3. Enable the **"Use Google Flow"** toggle on the node
4. Connect inputs/outputs and click **Run**
5. The extension automatically sends requests through Google Flow and returns results

---

## Updates

The extension is automatically updated by Komfy Studio:

- On startup, Komfy Studio checks for newer versions on GitHub
- If a new version is available → automatically downloads and updates the extension folder
- After updating, go to Chrome → `chrome://extensions` → click **🔄 Reload** on the extension
- You can also click **Reinstall** in **Settings** → **Extension** to reinstall at any time

---

## Troubleshooting

### Extension not connecting?

1. Verify Komfy Studio is running
2. Verify you've opened a Google Flow tab and signed in
3. Wait 10-15 seconds for the extension to sync
4. Try reloading the extension in `chrome://extensions`

### Extension icon not turning green?

1. Click the extension icon in the Chrome toolbar
2. Check the popup displays connection status
3. Ensure you're on the correct Google Flow page

### "Not installed" in Settings?

1. Try clicking **Install Now** or **Reinstall**
2. Check your internet connection (needed to download from GitHub)
3. Verify the extension path in Settings → Extension

---

## System Requirements

| Requirement | Details |
|-------------|---------|
| Komfy Studio | v0.1.39 or later |
| Chrome / Chromium | v120 or later |
| Google Account | With access to Google Flow |
| OS | Windows 10/11 |
| Internet | Required for downloading and connecting to Google Flow |

---

## See Also

- [App Builder Guide](./app-builder-guide.en.md)
- [App Store Guide](./app-store-guide.en.md)
- <a href="https://github.com/tuyenhm68/komfy-extension" target="_blank">Extension source code on GitHub</a>
