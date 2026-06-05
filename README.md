<div align="center">

<!-- HERO -->
<a href="https://lindocode.com"><img src="https://dawn-unit-97b0.sdrowvieli1.workers.dev/creativehub/images/portfolio/icon.svg"
       width="36"
       style="vertical-align:-6px; margin-right:12px; " /></a>
<h1 style="font-size:2.4rem; font-weight:700; letter-spacing:0.5px; font-family: sans;">
  Lindocode Digital
</h1>
<a href="https://lindocode.com"><img src="https://dawn-unit-97b0.sdrowvieli1.workers.dev/creativehub/images/portfolio/slogan.svg" width="520" alt="INNOVATE · BUILD · SCALE" /></a>
<a href="https://portfolio.lindocode.com"><img src="https://dawn-unit-97b0.sdrowvieli1.workers.dev/creativehub/images/portfolio/studio.svg" width="560" alt="Portfolio — Web, Mobile, Backend and UI Systems" /></a>

<br/>
<br/>
<p style="max-width:620px; font-size:0.95rem; color:#555555; font-family: sans;">
  Premium web, mobile, and backend systems built with clarity,
  performance, and real-world purpose.
</p>
<!-- NAV -->
<br>
<p>
  <a href="https://lindocode.com"><img src="https://dawn-unit-97b0.sdrowvieli1.workers.dev/creativehub/images/portfolio/nav-studio.svg" height="28" alt="Studio" /></a>
  <img src="https://dawn-unit-97b0.sdrowvieli1.workers.dev/creativehub/images/portfolio/nav-dot.svg" height="28" alt="·" />
  <a href="https://lindocode.com/digitalhub"><img src="https://dawn-unit-97b0.sdrowvieli1.workers.dev/creativehub/images/portfolio/nav-digital-hub.svg" height="28" alt="Digital Hub" /></a>
  <img src="https://dawn-unit-97b0.sdrowvieli1.workers.dev/creativehub/images/portfolio/nav-dot.svg" height="28" alt="·" />
  <a href="https://lindocode.com/contact?theme=minimal"><img src="https://dawn-unit-97b0.sdrowvieli1.workers.dev/creativehub/images/portfolio/nav-contact.svg" height="28" alt="Contact" /></a>
</p>

<br>

<!-- BADGES -->
<a href="https://lindocode.com"><img src="https://img.shields.io/badge/STUDIO-LINDOCODE%20DIGITAL-0E0E0E?style=for-the-badge"/></a>
<a href="https://lindocode.com"><img src="https://img.shields.io/badge/FOCUS-WEB·MOBILE·SYSTEMS-0E0E0E?style=for-the-badge"/></a>
<a href="https://lindocode.com"><img src="https://img.shields.io/badge/BASED%20IN-SOUTH%20AFRICA-B27B32?style=for-the-badge"/></a>

</div>

<br>
<br>

## Welcome

LazyAuthor is designed to make writing both traditional books and interactive stories simple.

Whether you're creating a novel, a branching adventure, a visual novel, or a gamebook, this guide will walk you through every step of the process.

### What you can create

- Interactive stories with branching choices
- Variable-driven narratives
- Visual novel style experiences
- Traditional ebooks
- EPUB exports
- Multimedia-enhanced stories

# LazyAuthor | Feature Reference

## Table of Contents

1. [Getting Started](#1-getting-started)
2. [Interactive Story Editor](#2-interactive-story-editor)
   - [Scene Management](#21-scene-management)
   - [Scene Types](#22-scene-types)
   - [Narrative Body](#23-narrative-body)
   - [Choices & Branching](#24-choices--branching)
   - [Choice Effects](#25-choice-effects)
   - [Choice Conditions](#26-choice-conditions)
   - [Variables](#27-variables)
   - [Player Input Scenes](#28-player-input-scenes)
   - [Media](#29-media)
   - [Story Metadata](#210-story-metadata)
   - [Theme](#211-story-theme)
   - [Preview](#212-preview)
   - [Import & Export](#213-import--export)
3. [Book Editor](#3-book-editor)
   - [Chapter Management](#31-chapter-management)
   - [Chapter Editor](#32-chapter-editor)
   - [Images](#33-images)
   - [Book Metadata](#34-book-metadata)
   - [Theme](#35-book-theme)
   - [Preview](#36-preview)
   - [Import & Export](#37-import--export)
4. [Auto-Save & Sync](#4-auto-save--sync)
5. [Account Management](#5-account-management)

---

## 1. Getting Started

1. Open [lazyauthor.lindocode.com](https://lazyauthor.lindocode.com) and create a free account.
2. On the **Select** screen, choose your format:
   - **Interactive Story** — branching fiction with choices, variables, and conditions.
   - **Book** — standard ebook with chapters, a table of contents, and cover art.
3. Your work saves automatically as you type. Switch modes at any time via the account menu → *Change mode*.

---

## 2. Interactive Story Editor

The story editor is a three-column layout: **Scene list** (left) · **Scene editor** (centre) · **Meta panel** (right).

---

### 2.1 Scene Management

| Action | How |
|--------|-----|
| Add scene | Click **+** in the scene list header |
| Select scene | Click any scene in the list |
| Rename scene | Edit the title field at the top of the scene editor |
| Delete scene | Click **×** next to the scene in the list |
| Set start scene | Click **▶** next to any scene — the reader always begins here |

**Start scene** — exactly one scene is marked as the start. It is shown with a `▶` indicator. Readers begin here when they open the exported EPUB.

**Deleted scene cleanup** — when a scene is deleted, all choices pointing to it and all `inputNextSceneId` references are automatically removed from other scenes.

---

### 2.2 Scene Types

Each scene has one of three types, set in the **Scene type** section.

#### Narrative (default)
The standard scene type. Has a narrative body and an optional choices panel. Readers read the text then pick a choice to proceed.

#### Player Input
Captures a value from the reader and stores it in a variable.

- Switching to Player Input preserves existing choices. They are removed only once you select a **Next scene after submit**.
- Full configuration in [Player Input Scenes](#28-player-input-scenes).

#### Ending
Marks a branch as complete. No choices are shown; the story ends at this scene for any path that reaches it.

- Switching to Ending when choices exist shows a confirmation prompt before clearing them.

---

### 2.3 Narrative Body

The large textarea holds the scene's prose.

**Variable interpolation** — insert `{{variableName}}` anywhere in the body to display the current value at read time.

| Syntax | Effect |
|--------|--------|
| `{{name}}` | Display current value |
| `{{score + 5}}` | Display value + 5 (read-only, does not mutate) |
| `{{score++}}` | Display value + 1 (read-only) |
| `{{score--}}` | Display value − 1 (read-only) |
| `{{score * 2}}` | Display value × 2 (read-only) |
| `{{score / 2}}` | Display value ÷ 2 (read-only) |

**Media markers** — when media is attached, control its position in the narrative with inline markers:

| Marker | Inserts |
|--------|---------|
| `[image]` | First attached image |
| `[image2]`, `[image3]` … | Subsequent images |
| `[audio]` | Audio player |
| `[video]` | Video player |
| `[break]` | Scene break divider (uses theme divider symbol) |

If no markers are used, media is appended after the body text.

---

### 2.4 Choices & Branching

The **Choices** collapsible section appears on Narrative scenes only.

**Adding a choice**
1. Type the choice text in the input field.
2. Select the target scene from the dropdown.
3. Press **Enter** or click **Add**.

**Editing a choice** — click into any existing choice row to change its text or target scene inline.

**Deleting a choice** — click **×** on the choice row.

Each choice links to exactly one target scene. Add as many choices as needed. Choices render as buttons in the order they appear.

---

### 2.5 Choice Effects

Effects run when the reader selects a choice, mutating one or more variables before the next scene loads.

**Adding an effect**
1. Expand a choice row.
2. Click **+ Effect**.
3. Select a variable, an operation, and a value.

**Operations**

| Operation | Result |
|-----------|--------|
| `set` | Assigns `value` directly to the variable |
| `add` | `variable = variable + value` |
| `subtract` | `variable = variable − value` |
| `multiply` | `variable = variable × value` |

Multiple effects can be stacked on a single choice and run in order.

---

### 2.6 Choice Conditions

A condition gates a choice — it is only shown to the reader if the condition evaluates to `true` at runtime.

**Setting a condition**
1. Expand a choice row.
2. Click **Set condition**.
3. Select a variable, an operator, and a comparison value.

**Operators**

| Operator | Meaning |
|----------|---------|
| `eq` | Equal to |
| `ne` | Not equal to |
| `gt` | Greater than |
| `gte` | Greater than or equal to |
| `lt` | Less than |
| `lte` | Less than or equal to |

One condition is supported per choice. To combine multiple conditions, chain scenes: gate scene A with condition 1, then gate a choice inside it with condition 2.

**Removing a condition** — click **Remove condition** inside the choice row.

---

### 2.7 Variables

Variables are named values that persist across scenes. Open the **Variables** panel via the toolbar button (shows a count badge when variables exist).

**Variable fields**

| Field | Description |
|-------|-------------|
| Name | Identifier used in `{{name}}` templates and condition/effect selectors. No spaces. |
| Label | Human-readable name shown in the editor UI. |
| Type | `text` or `number`. Numbers enable arithmetic operations and numeric comparisons. |
| Default value | Assigned when the story starts. |

**Variable lifecycle**
- Initialised to their default values when a reader starts the story.
- Effects on choices mutate values during play.
- `{{name}}` in narrative bodies and input prompts reads the current value.
- Deleting a variable automatically removes all effects and conditions that reference it across every scene.

---

### 2.8 Player Input Scenes

An input scene pauses the reader, shows a prompt, and stores their response in a variable.

**Core fields**

| Field | Description |
|-------|-------------|
| Prompt | Text displayed above the input field (e.g. *"What is your name?"*) |
| Store in variable | The variable that receives the reader's response |
| Next scene after submit | Where the reader goes after a valid submission. Selecting this clears any existing choices on the scene. |

**Input type** — controls the HTML input rendered to the reader:

| Type | Use case |
|------|----------|
| `text` (default) | Any string |
| `number` | Numeric input only |
| `password` | Hidden characters (e.g. a code word or PIN) |

**Validation** — optional. Reject wrong answers and retry or redirect.

| Setting | Description |
|---------|-------------|
| Match type | `exact` — must match exactly; `contains` — must include the value; `regex` — must match the regular expression |
| Correct answer | Expected value. Leave blank to accept any input. |
| Case-sensitive | Capitalisation must match when enabled |
| Error message | Shown to the reader on a wrong answer |
| On wrong answer → scene | Redirect on failure (default: stay and retry) |
| Max attempts | Tries before redirecting to the fail scene (0 = unlimited) |

**Time limit** — optional countdown in seconds.

| Setting | Description |
|---------|-------------|
| Countdown (seconds) | 0 = disabled |
| On timeout → scene | Redirect when time runs out |

**Submission limit** — optional cap on total submissions across the session.

| Setting | Description |
|---------|-------------|
| Max submissions | 0 = unlimited |
| On limit reached → scene | Redirect when the limit is hit |

---

### 2.9 Media

Managed in the **Media** collapsible section of each scene.

**Images**
- Upload one or more images (PNG, JPG, WebP, GIF).
- Stored in Supabase Storage and referenced by URL.
- Placed inline with `[image]`, `[image2]`, `[image3]` markers, or appended automatically.
- Remove by clicking **×** on the thumbnail.

**Audio**
- Single audio file per scene (MP3, OGG, WAV).
- Options: **Autoplay**, **Loop**, **Hide controls** (audio runs but no player UI is shown).
- Placed with `[audio]` marker.

**Video**
- Single video file per scene (MP4, WebM).
- Placed with `[video]` marker.

All media is tied to the story's ID. Deleting the story or loading a new one cleans up orphaned files in Supabase Storage.

---

### 2.10 Story Metadata

Edited in the **Meta** panel on the right side of the editor.

| Field | Description |
|-------|-------------|
| Title | Story title — used in the EPUB manifest and cover page |
| Author | Author name — written to EPUB metadata |
| Language | BCP-47 language code (e.g. `en`, `fr`, `zu`) |
| Cover image | Displayed on the EPUB cover page |

---

### 2.11 Story Theme

Open via the **Theme** toolbar button. Controls the visual presentation of the exported EPUB.

**Body typography**

| Setting | Options / Example |
|---------|-------------------|
| Font family | CSS font-family string, e.g. `Georgia, serif` |
| Font size | `1em`, `16px` |
| Line height | `1.9`, `28px` |
| Text alignment | Left / Justify |
| Body padding | `1.5em 2em` |
| Text indent | `1.2em` |
| Text colour | Any CSS colour |

**Title / h1**

| Setting | Options |
|---------|---------|
| Title size | CSS size |
| Title style | Normal / Italic |
| Title weight | Normal / Bold |
| Title alignment | Left / Centre |
| Letter spacing | CSS value |
| Decoration | None / Rules (horizontal rules above and below) |

**Choice buttons**

| Setting | Options |
|---------|---------|
| Style | Outline / Filled |
| Colour | CSS colour |
| Border radius | Pill / Rounded / Square |

**Input form** (Player Input scenes)

| Setting | Options |
|---------|---------|
| Field style | Line (underline only) / Box (full border) |
| Colour | CSS colour |
| Submit button style | Outline / Filled |
| Submit radius | Pill / Rounded / Square |

**Images**

| Setting | Options |
|---------|---------|
| Max width | `100%`, `480px` |
| Alignment | Left / Centre / Right |

**Section divider**

| Setting | Description |
|---------|-------------|
| Symbol | Characters shown between sections, e.g. `* * *`, `—`, `✦` |
| Colour | CSS colour |

---

### 2.12 Preview

Click **Preview** in the scene editor header to toggle a live read-only view of the current scene. The preview renders:

- Narrative body with `{{variable}}` expressions interpolated using default values.
- Choices as styled buttons with the active theme applied.
- Media in its inline marker position.
- Conditions evaluated against default variable values (a conditioned choice is hidden if the default does not satisfy it).

Click **Edit** to return to the editor.

---

### 2.13 Import & Export

**Export EPUB**
- Click **Export EPUB** in the toolbar.
- The EPUB 3 file is built entirely in the browser — no server upload, no waiting.
- Output: cover page · all scenes rendered with the active theme · embedded JavaScript runtime for branching navigation · all media embedded.
- Compatible with **Lazy Reader** and any EPUB 3 reader that supports scripted EPUBs.

**Import EPUB**
- Account menu → **Import EPUB**.
- Parses an existing `.epub` file and maps its content to scenes.
- Replaces the current story (confirmation required if the story has content).
- Import warnings (unsupported features, skipped content) appear in a dismissible banner.

---

## 3. Book Editor

The book editor is a three-column layout: **Chapter list** (left) · **Chapter editor** (centre) · **Meta panel** (right).

---

### 3.1 Chapter Management

| Action | How |
|--------|-----|
| Add chapter | Click **+ Add chapter** at the bottom of the chapter list |
| Select chapter | Click any chapter row |
| Rename chapter | Edit the title field at the top of the chapter editor |
| Delete chapter | Hover a row → click **×** (only available when more than one chapter exists) |
| Reorder | Hover a row → click **▲** or **▼** |

**Chapter numbering** — numbers are computed from position. The `chapterStartAt` meta field controls which index receives number 1, useful for books with a prologue or unnumbered front matter.

---

### 3.2 Chapter Editor

- **Title field** — the chapter title, used in the body heading and the auto-generated table of contents.
- **Edit / Preview toggle** — switch between the prose editor and the chapter preview.
- **Narrative textarea** — the chapter body in plain text with inline marker support.

**Inline markers**

| Marker | Inserts |
|--------|---------|
| `[image]` | First attached image |
| `[image2]`, `[image3]` … | Additional images |
| `[break]` | Scene break divider (uses theme divider symbol) |

If no markers are used, images are appended after the body text.

---

### 3.3 Images

- Upload images from the chapter editor (PNG, JPG, WebP, GIF).
- Multiple images can be attached per chapter.
- Stored in Supabase Storage and embedded in the exported EPUB.
- Remove via **×** on the thumbnail.
- Control placement with `[image]` markers in the body.

---

### 3.4 Book Metadata

Edited in the **Meta** panel on the right side of the editor.

| Field | Description |
|-------|-------------|
| Title | Book title — used in the EPUB manifest and cover page |
| Author | Author name — written to EPUB metadata |
| Description | Short synopsis, written to the EPUB description field |
| Language | BCP-47 language code |
| Cover image | Displayed on the EPUB cover page |
| Chapter start at | 0-based index of the first numbered chapter. Set to `1` to make index 0 a prologue (unnumbered), with index 1 becoming Chapter 1. |

---

### 3.5 Book Theme

Open via the **Theme** toolbar button.

**Body typography**

| Setting | Options / Example |
|---------|-------------------|
| Font family | `Georgia, serif` |
| Font size | `1em` |
| Line height | `1.9` |
| Text colour | CSS colour |
| Body margin | `1.5em 1.8em` |
| Text alignment | Left / Justify |
| Text indent | `1.2em` |

**Chapter number label**

| Setting | Options |
|---------|---------|
| Visible | Show / hide the "Chapter N" label above the title |
| Colour | CSS colour |
| Letter spacing | CSS value |

**Decorative rules around title**

| Setting | Options |
|---------|---------|
| Show rules | Enable / disable horizontal rules above and below the title |
| Rule colour | CSS colour |
| Rule width | CSS width, e.g. `40%` |

**Chapter title (h1)**

| Setting | Options |
|---------|---------|
| Title size | CSS size |
| Title style | Normal / Italic |
| Title weight | Normal / Bold |
| Letter spacing | CSS value |

**Scene break divider**

| Setting | Description |
|---------|-------------|
| Symbol | Characters between sections, e.g. `* * *` |
| Colour | CSS colour |

**Table of contents page**

| Setting | Description |
|---------|-------------|
| TOC title colour | Colour of the "Contents" heading |
| TOC title letter spacing | CSS letter-spacing |
| TOC entry dot colour | Colour of the leader dots |

---

### 3.6 Preview

Click **Preview** in the chapter editor header to see an iframe rendering of the chapter exactly as it will appear in the EPUB — chapter number, decorative rules, title, body text, images, and dividers all rendered with the active theme.

Click **Edit** to return.

---

### 3.7 Import & Export

**Export EPUB**
- Click **Export EPUB** in the toolbar.
- Built in the browser — no server upload.
- Output: cover page · auto-generated table of contents · all chapters with the active theme · embedded images.
- Compatible with Kindle (via Calibre), Apple Books, Kobo, and any standard EPUB 3 reader.

**Import EPUB**
- Account menu → **Import EPUB**.
- Content is mapped to chapters automatically.
- Replaces the current book (confirmation required if the book has content).

**Import .docx**
- Account menu → **Import .docx**.
- Imports a Microsoft Word document, splitting content into chapters based on heading structure.
- Replaces the current book (confirmation required).

---

## 4. Auto-Save & Sync

LazyAuthor uses a two-layer persistence strategy so your work is never lost.

| Layer | Behaviour |
|-------|-----------|
| **localStorage** | Written immediately on every change. Provides instant load on the next visit even without internet. |
| **Database cloud** | Written 1.5 seconds after the last change (debounced). Cloud copy is authoritative — it overwrites localStorage on load if a newer cloud version exists. |

**Sync status indicator** in the toolbar:

| Status | Meaning |
|--------|---------|
| `Saving…` | A debounced write is pending or in progress |
| `Saved` | Cloud and local are in sync |
| `Save failed` | A database write error occurred (shown in red). Local copy is still intact. |

Story and book data are stored independently. Switching formats does not affect the other format's data.

---

## 5. Account Management

Accessed via the email address button in the top-right of the toolbar.

| Action | Description |
|--------|-------------|
| Change mode | Return to the mode selection screen |
| Import EPUB | Replace current story/book from an `.epub` file |
| Import .docx | *(Book editor only)* Replace current book from a Word document |
| Sign out | End the session |
| Delete account | Permanently deletes the account, all story/book data, and all uploaded media from database. **This cannot be undone.** |

<br>


<div align="center">
<br/>

<p>
  <a href="https://lindocode.com/terms?theme=minimal" style="text-decoration: none; color: #B27B32; font-family: sans-serif; font-weight: 600;"><strong >Terms</strong></a>
  ·
  <a href="https://lindocode.com/privacy?theme=minimal" style="text-decoration: none; color: #B27B32; font-family: sans-serif; font-weight: 600;"><strong>Privacy</strong></a>
</p>

<sub>© Lindocode Digital · South Africa</sub>

</div>
