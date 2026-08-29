# 🧩 Skill Guide

> Reusable prompt recipes. Type a single `/` in any prompt box of any app to call one up.

## Table of Contents

- [Overview](#overview)
- [Three Kinds of Skill](#three-kinds-of-skill)
- [Getting Started](#getting-started)
- [Multi-Step Skills](#multi-step-skills)
- [Skill Hub](#skill-hub)
- [Managing Your Skills](#managing-your-skills)
- [Configuring the Language Model](#configuring-the-language-model)
- [Troubleshooting](#troubleshooting)

---

## Overview

Writing a good prompt is the hardest part of using image and video models. A **Skill** packages that difficulty into something you can summon with one slash.

Skills work in **every prompt box of every app**, not just Chat — MiniMax H3, LTX, WAN, and the apps you build yourself with App Builder all have them.

Each skill declares which app and mode it serves, so the picker only shows skills that fit where you're standing — you won't see a music skill while working in I2V mode.

---

## Three Kinds of Skill

| Kind | How it works | Needs internet | Needs API key |
|------|--------------|----------------|---------------|
| **Template** | Inserts a prompt skeleton into the box for you to fill in | No | No |
| **LLM** | You type a short brief, a language model writes the full prompt | Yes | Yes |
| **Multi-step** | Asks questions, generates images, waits for approval, then generates video | Yes | Yes |

> 💡 **Tip**: Template skills work immediately after installing, with no configuration. If you don't have an API key, start with these.

---

## Getting Started

### Step 1: Open the skill picker

Two ways, whichever suits you:

- **Type `/`** in the prompt box — the slash must stand alone (at the start of the box, or after a space)
- **Click the puzzle-piece icon** in the toolbar below the prompt box

### Step 2: Find a skill

The picker has a search box and category tabs:

- **All** — every skill that fits the current prompt box
- **My Skills** — skills you created or installed
- **Featured** — highlighted skills from the hub

The list also includes **hub skills you haven't installed**, listed after the ones already on your machine. Picking one installs it and uses it right away, so you don't have to abandon the sentence you're writing.

> 💡 **Accent-insensitive search**: Typing `giay` still finds the skill named `giấy`. Diacritics are optional.

### Step 3: Use the skill

It depends on the kind:

**Template skills** insert the prompt skeleton straight into the box. Fill in the blanks and run as usual.

**LLM skills** attach the skill name as a chip in the box. Type a short brief, click **Write prompt**, and the skill returns a finished prompt.

Once a skill has written a prompt, it also shows its **assumptions** — details it filled in because you didn't specify them. Read this to check it understood you. If not, undo and write a more specific brief.

---

## Multi-Step Skills

This is the most capable kind, and it only runs in **Chat**.

Instead of writing a prompt and stopping, a multi-step skill drives the whole process:

1. You describe an idea, e.g. *"a video of a cat playing in a kitchen, paper-collage style"*
2. The skill **asks questions** to pin down the direction — how many shots, aspect ratio, background music or not
3. The skill **generates images** for each shot
4. The skill **stops and waits for your approval** — approve to continue, or send it back for another try
5. The skill **generates video** from the approved images

All of it happens in a single card inside the conversation, with buttons to answer, cancel, and continue.

### Runs survive an app restart

A run lives outside the UI, so switching conversations won't lose it.

- A run **waiting for your answer** is restored completely — reopen the app and the question is still there for you to answer
- A run that was **mid-execution** is marked interrupted, because the system can't tell whether it stopped between a model call or between video generations. You restart it from that point

History keeps the **10 most recent runs from the last 7 days**.

---

## Skill Hub

Open **Skill** in the sidebar to reach the Skill Hub. There are two tabs:

### Discover tab

The shared library contributed by the community. Filter by category, sort by popularity. Click a skill to read its full description before installing.

### My Skills tab

Everything currently on your machine, filterable by source:

| Source | Meaning |
|--------|---------|
| **Builtin** | Ships inside the app; upgrading the app upgrades these |
| **Store** | Installed from Skill Hub |
| **User** | Created or imported by you |

When two skills share a slug, priority is **user > store > builtin** — your own skill always wins.

### Publishing to the hub

In the My Skills tab, select a skill and use the publish action. Fill in the description and category, then submit. Your skill will appear in other people's Discover tab.

---

## Managing Your Skills

- **Disable** — turn off skills you don't use to keep the picker short, without uninstalling them
- **Uninstall** — for skills installed from the hub
- **Import / export** — skills package into a file you can share or back up

A skill's slug is what you type after `/`, so it must be **lowercase letters, digits and hyphens** — for example `paper-collage-explainer`.

---

## Configuring the Language Model

**LLM** and **multi-step** skills need a language model. Template skills don't.

1. Open **Settings**
2. Enter your **OpenAI API key**
3. Change the model if you want something other than the default

> ⚠️ **Note**: This calls a third-party API, so it is **billed per use** and requires internet — unlike image and video generation, which runs entirely on your own machine. If you want to stay fully offline, stick to Template skills.

---

## Troubleshooting

### Typing `/` doesn't open the picker

The slash must **stand alone** — at the start of the box, or with a space before it. Typing `abc/` won't open it. Try the puzzle-piece icon instead.

### The picker is empty or missing a skill I know I have

Skills are filtered by the app and mode you're currently in, so skills written for a different mode won't appear. Also check whether the skill is disabled in the **My Skills** tab.

### An LLM skill reports a missing key

You haven't entered an OpenAI API key in Settings. See [Configuring the Language Model](#configuring-the-language-model).

### A multi-step skill stopped after I reopened the app

This is deliberate. A mid-execution run can't be restored, because there's no way to know whether it stopped between a model call or between video generations — the system marks it interrupted rather than pretending to continue and producing a wrong result. Restart it from that step.

### The skill wrote a prompt that misses my intent

Read the **assumptions** the skill returned — they list what it filled in on your behalf. Undo, then write a more specific brief covering exactly those points.

---

## See Also

- [💬 Chat Guide](./chat-guide.en.md)
- [🏗️ App Builder Guide](./app-builder-guide.en.md)
- [🛒 App Store Guide](./app-store-guide.en.md)
