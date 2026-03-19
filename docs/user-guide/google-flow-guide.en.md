# 🎬 Google Flow Mode Guide

> Use **Komfy Bridge Extension** to generate AI videos (Veo 3.1) and AI images (Nano Banana) directly via Google Flow — free, no API key required.

## Table of Contents

- [Overview](#overview)
- [Initial Setup](#initial-setup)
- [Using the Veo 3.1 Node](#using-the-veo-31-node)
  - [Ingredients Mode](#ingredients-mode-reference-images)
  - [Advanced Settings](#advanced-settings)
- [Using the Nano Banana Node](#using-the-nano-banana-node)
- [Checking Connection Status](#checking-connection-status)
- [Troubleshooting](#troubleshooting)

---

## Overview

**Google Flow Mode** lets Komfy Studio control Google Flow through the Komfy Bridge Extension. Instead of calling APIs directly (which requires API keys and quota), the system will:

1. Automatically open/navigate to the Google Flow tab in Chrome
2. Automatically enter prompts and reference images
3. Trigger video/image generation
4. Download the result and display it in the node

| Node | Function | Requirement |
|------|----------|-------------|
| **Veo 3.1** | AI video generation (Text-to-Video, Image-to-Video) | Google account with Veo access |
| **Nano Banana 2** | AI image generation | Google account with Flow access |
| **Nano Banana Pro** | High-quality AI image generation | Google account with Flow access |

---

## Initial Setup

### Step 1: Install Komfy Bridge Extension

1. Open **Komfy Studio** → **Settings** → **Extension** tab
2. Click **Install Now** if not yet installed
3. Copy the extension path displayed
4. Open Chrome → `chrome://extensions` → enable **Developer mode** → **Load unpacked** → paste the path
5. **Komfy Bridge** extension appears in the Chrome toolbar

### Step 2: Connect to Google Flow

1. Ensure **Komfy Studio is running**
2. In Chrome, open <a href="https://labs.google/fx/tools/flow" target="_blank">labs.google/fx/tools/flow</a>
3. Sign in with a Google account that has Veo / Flow access
4. Wait **10–15 seconds** for the extension to sync

### Step 3: Verify the Connection

Click the **Komfy Bridge** icon in the Chrome toolbar — the popup shows:

```
Komfy Studio    ● Connected
Google Session  ● Active
Project         af9ec403-aa36-...
Last sync       2s ago
```

If you see **Connected** + **Active** → ready to use ✅

---

## Using the Veo 3.1 Node

### Enabling Google Flow Mode

1. Open **Workflows** → drag the **Veo 3.1** node onto the canvas
2. Click the ⚙️ (Settings) icon on the node
3. Enable the **Use Google Flow** toggle → a 🔌 icon appears in the node header
4. Connect a **Prompt** from a Text node

> ⚠️ **Note:** When Google Flow is enabled, the **Resolution** and **Duration** settings are hidden (API mode only). Instead, **Video Type** and **Orientation** appear.

### Ingredients Mode (Reference Images)

The default mode — best for generating videos with a specific style or subject from reference images.

**How to use:**

```
[Text Node]  ──────────►  Prompt *
[Image Node] ──────────►  Image 1
[Image Node] ──────────►  Connect for more slots (up to 4)
                                ↓
                          [Veo 3.1 Node]  ──►  Video
```

- **Image 1**: First reference image (style, character, product, ...)
- **Image 2–4**: Connect up to 4 reference images
- New empty slots appear automatically as you connect each one

**Example workflow:**

```
Text (prompt)   ──► Veo 3.1 (Ingredients) ──► Video Output
Image (product) ──►
Image (style)   ──►
```

### Advanced Settings

Open Settings (⚙️) on the Veo 3.1 node:

| Setting | Values | Description |
|---------|--------|-------------|
| **Use Google Flow** | On/Off | Enable/disable Flow mode |
| **Veo Model** | Veo 3.1 - Fast / Quality | Fast = quicker generation, Quality = higher quality |
| **Video Type** | Ingredients | Reference image mode (current) |
| **Orientation** | Landscape / Portrait | Aspect ratio: 16:9 / 9:16 |

---

## Using the Nano Banana Node

### Nano Banana 2 / Nano Banana Pro

Works the same as Veo 3.1 but generates **images** instead of videos.

**Setup:**

1. Drag **Nano Banana 2** or **Nano Banana Pro** onto the canvas
2. Click ⚙️ → enable **Use Google Flow**
3. Connect a Prompt and (optionally) reference images

**Input structure:**

```
[Text Node]  ──────────►  Prompt *
[Image Node] ──────────►  Image 1     (optional)
[Image Node] ──────────►  Image 2     (optional)
                                ↓
                     [Nano Banana] ──►  Image Output
```

**Settings:**

| Setting | Values | Description |
|---------|--------|-------------|
| **Use Google Flow** | On/Off | Enable Flow mode |
| **Orientation** | Landscape / Portrait | Image aspect ratio |

---

## Checking Connection Status

### On the Node

When **Use Google Flow = On**, the node header shows a green 🔌 icon. Hover over it for details:

```
🔌 Google Flow active
Model: Veo 3.1 - Fast
Type: Ingredients
Orientation: Landscape
```

### In the Extension Popup

Click the Komfy Bridge icon in the Chrome toolbar:

| Status | Meaning |
|--------|---------|
| `● Connected` | Komfy Studio is connected to the extension |
| `● Active` | Google session is active (token available) |
| `Project: xxx` | Current project ID on Google Flow |
| `Last sync: Xs ago` | Time since last sync |

### In Komfy Studio Settings

**Settings** → **Extension** → view detailed status of each connected Chrome profile.

---

## Troubleshooting

### ❌ "Komfy Bridge extension is not connected"

The node shows this error when the extension is not connected or has just disconnected.

**Solution:**
1. Open Chrome and ensure a Google Flow tab is open
2. Wait 10–30 seconds (the extension reconnects automatically)
3. Click **Sync** in the extension popup
4. If still failing: reload the extension in `chrome://extensions`

> 💡 This error usually occurs when Chrome has been idle for a while. Simply re-running the node is often sufficient — the system automatically waits up to 16 seconds for the extension to reconnect.

### ❌ Extension creates a new project instead of using the existing one

The extension automatically creates a **"komfy-studio"** project on Google Flow if it can't find one. If a new project is created each time:

1. Delete the broken old project on Google Flow
2. Reload the extension → re-run the node
3. The extension will find the existing "komfy-studio" project or create exactly one new one

### ❌ One node's video/image shows in another node

This issue is fixed in **v2.0.79+** using session token isolation.

If you still experience this:
1. Run nodes one at a time instead of in parallel
2. Ensure you're using extension **v2.0.79** or later (visible in the popup)

### ❌ Results are slow or missing

Google Flow may take **1–5 minutes** to generate video depending on complexity:

- **Ingredients + no reference images**: ~1–2 minutes
- **Ingredients + reference images**: ~2–4 minutes
- **Veo 3.1 Quality**: ~3–5 minutes

Monitor the progress bar on the node to track status.

---

## See Also

- [Komfy Bridge Extension Guide](./chrome-extension-guide.en.md)
- [App Builder Guide](./app-builder-guide.en.md)
- <a href="https://labs.google/fx/tools/flow" target="_blank">Google Flow (labs.google)</a>
