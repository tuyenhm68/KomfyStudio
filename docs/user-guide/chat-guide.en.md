# 💬 Chat Guide

> Describe what you want to create and KomfyStudio picks the model and mode for you. No app to open, no workflow to wire.

## Table of Contents

- [Overview](#overview)
- [Requirements](#requirements)
- [Getting Started](#getting-started)
- [Screen Layout](#screen-layout)
- [Choosing Output Type and Model](#choosing-output-type-and-model)
- [Attaching Files](#attaching-files)
- [The Plan Summary](#the-plan-summary)
- [Project Gallery](#project-gallery)
- [Conversations](#conversations)
- [Using Skills in Chat](#using-skills-in-chat)
- [Troubleshooting](#troubleshooting)

---

## Overview

**Chat** is a way to use KomfyStudio without going through an app. You type a description, attach images/videos/audio if you have them, and KomfyStudio reads that combination of inputs to build the run: it picks the model, picks the mode, and assigns each file to the right slot.

| You do this | KomfyStudio does this |
|-------------|-----------------------|
| Type a description, attach nothing | Runs Text to Video |
| Attach 1 image | Switches to Image to Video, image becomes the first frame |
| Attach 1 audio file | Switches to Audio Drive (lip-sync) |
| Attach 1 video | Switches to Extend Video |
| Change model mid-way | Recomputes the plan, warns if the new model can't take your attachments |

This routing runs on **plain rules** — the same input always gives the same result. No network calls, no guessing.

> 💡 **Important**: Chat **does not read the words you type** to decide between image, video, and music. Output type is chosen manually via the tabs in the model panel — see [Choosing Output Type and Model](#choosing-output-type-and-model).

---

## Requirements

- **A running backend**: ComfyUI Local or whichever backend you use
- **At least one installed model** for the output type you want

Chat reuses the models and workflows you already installed for the apps — **nothing extra to download**. Hardware requirements depend on the model you choose to run.

> ⚠️ **Note**: Chat runs on its own balanced defaults and **does not read your app settings**. Whatever you tuned inside the MiniMax H3 app, Chat still uses its own defaults.

---

## Getting Started

### Step 1: Open Chat

1. Launch **KomfyStudio** and make sure the backend is running
2. Select **Chat** in the sidebar (speech bubble icon)

### Step 2: Choose output type and model

Click the model chip at the bottom of the composer (it shows `MiniMax H3` by default). The panel that opens has three tabs at the top: **Video** · **Image** · **Music**.

1. Pick the tab matching what you want to create
2. Pick a model from the list below

### Step 3: Type and send

1. Enter your description in the composer
2. Attach files if needed (paperclip icon)
3. Check the **plan summary** just above the button row — it states exactly what will run
4. Press the send button (up arrow) or `Enter`

> 💡 **Tip**: The summary line, e.g. `MiniMax H3 · T2V · 960×544 · 5s · native`, is the single most useful thing on screen. If it doesn't say what you meant, fix it before sending.

---

## Screen Layout

The Chat screen has two main areas:

- **Chat column** — the open conversation and the composer
- **Gallery** — every result in the current project

Use the layout button at the right of the filter bar to switch between four modes:

| Mode | Description |
|------|-------------|
| **Chat on left** | Default — chat left, gallery right |
| **Chat on right** | Swaps the two columns |
| **Chat only** | Hides the gallery, chat takes the full width |
| **Gallery only** | Hides chat, results full screen |

> 💡 **Shortcut**: `Ctrl` + `\` flips quickly between chat-left and chat-right.

Drag the divider between the columns to resize. Layout and width are remembered for next time.

---

## Choosing Output Type and Model

This is the easiest thing to get wrong, so it's worth spelling out.

**The default output type is Video.** Typing "make a sad lofi track" without switching tabs still runs Text to Video — routing follows the tab and your attachments, not the meaning of your sentence.

### How to create music

1. Click the model chip at the bottom of the composer
2. Select the **Music** tab
3. Select **MiniMax Music 3**
4. Describe the genre/mood and send

The summary line should now read `MiniMax Music 3 · Music · 60s`. If it still says `T2V`, the tab hasn't changed.

### Adding lyrics

Write the description first, then a new line starting with `lyrics:`:

```
sad lofi, soft piano, rain in the background
lyrics:
Empty streets tonight
Just me and the rain
```

Everything before `lyrics:` becomes the genre description, everything after becomes the lyrics. Track length is adjustable between **10 and 300 seconds**, defaulting to 60.

### Model is remembered per type

Each output type remembers its own model: choosing LTX 2.5 for video doesn't affect your image or music model. Choices are stored per backend, since a local ComfyUI install and another backend won't have the same models.

> ⚠️ **Note**: The output type is **not persisted** between sessions. Restarting KomfyStudio resets Chat to Video, even if you were working on music last time.

---

## Attaching Files

Click the **paperclip** at the bottom of the composer and pick images, video, or audio. You can select several files at once.

The mode is derived from the **number and type of files**, not from your wording. With MiniMax H3:

| Attachments | Selected mode |
|-------------|---------------|
| Nothing | **T2V** — Text to Video |
| 1 image | **I2V** — Image to Video (image becomes first frame) |
| 2 images | **I2V** — first frame + last frame |
| 3 or more images | **R2V** — Reference to Video |
| 1 video | **Extend** — extend the video |
| 1 image + 1 video | **R2V** — image as character, video as motion |
| 1 audio | **Audio Drive** — lip-sync |
| 1 audio + 1 image | **Audio Drive** — audio drives the character's mouth |

Other models declare different modes, so this table is specific to MiniMax H3. The principle is the same everywhere: each mode declares how many images/videos/audio files it accepts, and the system picks the mode that best fits what you attached.

Each attachment appears as a chip in the composer, labelled with the role it plays (`First frame`, `Reference image`, `Audio track`…).

---

## The Plan Summary

Just above the button row is a line stating exactly what will run:

```
MiniMax H3 · I2V · 960×544 · 5s · native
```

### The Adjust button

Click **Adjust** to expose three options:

- **Aspect ratio**
- **Quality tier** — Draft / Balanced / Sharp
- **Duration** — in seconds

Everything else is decided by the model; Chat doesn't surface it, to keep the composer compact.

### Model-switch warning

If your chosen model can't take the files you attached, Chat **does not silently switch**. It builds the plan with a different model and shows an amber notice saying so explicitly.

### Disambiguation chips

When the same set of files has several close-scoring interpretations, Chat shows a row of chips — *"Use these files as:"* — so you decide, rather than it guessing.

---

## Project Gallery

The area beside the chat column holds **every result in the current project** — whether created by Chat or by an app — grouped by day.

### Filters

The top bar filters by:

- **Type** — image / video / music
- **Source** — from Chat or from an app
- **Model** — models that actually produced results in this project
- **Search** — by prompt or filename

### Reusing results

Open a result full screen and you get three options:

| Action | Result |
|--------|--------|
| **Use as input** | Attaches that result to the composer for your next turn |
| **Create variant** | Refills the composer with the original prompt to rerun with a new seed |
| **Open in app** | Jumps to the app that created it for deeper editing |

### Background jobs

A running job appears as a placeholder tile at the front of the "Today" group, with a cancel button. Jobs live outside the chat UI, so **switching conversations or closing the chat column will not cancel them**.

> ⚠️ **Note**: Jobs only live for the duration of the session. Quitting the app while a job runs loses that run; results already finished stay in the gallery.

---

## Conversations

Conversations belong to a **project**: switching projects switches both the conversation list and the gallery.

- Click **+** at the top of the chat column to start a new conversation
- The title is taken from your first message
- History is stored locally and survives restarts

Each message keeps a snapshot of its own run, so reopening a conversation later still shows which model ran and what it produced.

---

## Using Skills in Chat

Type `/` in the composer to open the skill picker, or click the puzzle-piece icon at the bottom of the composer. A skill writes the prompt for you instead of you starting from scratch.

Some skills are multi-step: they ask you a few questions, generate images, wait for your approval, and only then generate video.

See the [Skill Guide](./skill-guide.en.md) for details.

---

## Troubleshooting

### I asked for music but got a video

The output type is still set to Video. Chat doesn't read the meaning of your text. Click the model chip → **Music** tab → pick a music model. See [Choosing Output Type and Model](#choosing-output-type-and-model).

### "No model installed for this output type"

The output type you selected has no models. Install one through **Apps** or **Store**, then return to Chat.

### "No mode accepts this combination of files"

Your attachments exceed what the current model accepts — for example 5 images into a model that takes at most 4. Remove files, or switch model.

### The send button is greyed out

Send only enables when there is **both** text **and** a valid plan. An empty composer won't send, even with files attached.

### Attachment chips look faded when I reopen a conversation

Attachments from a previous session can't be persisted if they only existed in temporary memory. Those chips are marked expired — reattach the file and you can run again.

---

## See Also

- [🧩 Skill Guide](./skill-guide.en.md)
- [🎬 MiniMax H3 Guide](./minimax-h3-guide.en.md)
- [🛒 App Store Guide](./app-store-guide.en.md)
