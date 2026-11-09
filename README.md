# Chat Saver — Chrome Extension (Manifest V3)

**Author:** Soubhagyya  
**Project:** Bharat Space Education Research Centre (BSERC) Internship — Week 2 (Project 12)  
**Category:** Section C: Chrome Extensions  
**Platform:** Google Chrome / Chromium-based browsers (Manifest V3)

---

## Overview

**Chat Saver** is a high-productivity Chrome Extension that captures and archives long AI chat conversations into cleanly formatted Markdown (`.md`) or PDF documents with a single click. It preserves code syntax, programming languages, tables, and hierarchical headings without sending any data to external servers.

---

## Key Features

1. **Multi-Platform Support:**
   - Detects and parses conversations across major AI chat interfaces (ChatGPT, Claude, and standard web chat layouts).
   - Distinguishes between User and Assistant turns automatically.

2. **Formatting Preservation:**
   - **Code Blocks:** Preserves exact indentation, newlines, and programming language tags (`python`, `javascript`, etc.) so saved code remains runnable.
   - **Tables:** Preserves tabular data, converting HTML tables into clean GFM Markdown tables (`| Header | ... |`).
   - **Headings & Lists:** Maintains `h1`-`h4`, ordered numbers, bullet lists, and blockquotes.

3. **Full or Selective Export:**
   - **All Messages:** Exports the entire conversation thread in one click.
   - **Selective Mode:** Check or uncheck individual message turns to export only relevant excerpts.

4. **Dual Export Formats:**
   - **Markdown (`.md`):** Ideal for Obsidian, Notion, GitHub notes, and documentation.
   - **PDF:** Opens a print-optimized vector layout with syntax-highlighted code blocks, page numbers, and table borders, directly invoking Chrome's Print-to-PDF.

5. **Dynamic File Naming:**
   - Automatically derives the filename from the chat thread title, sanitized for Windows and Unix filesystems.

6. **100% Offline & Private:**
   - Operates entirely inside the browser tab using standard DOM APIs. Zero analytics, zero logins, zero network requests.

---

## Installation & Setup

1. Open Chrome and go to `chrome://extensions/`.
2. Enable the **Developer mode** toggle in the top-right corner.
3. Click **Load unpacked**.
4. Select the `chat-saver` folder.
5. Pin **Chat Saver** to your toolbar.

---

## Offline Testing & Demonstration

A comprehensive 52-message test fixture is included in the project: `sample_chat_50_messages.html`.

### Verification Steps:
1. Open `sample_chat_50_messages.html` directly in Chrome:
   ```
   file:///.../chat-saver/sample_chat_50_messages.html
   ```
2. Click the **Chat Saver** icon on your Chrome toolbar.
3. Observe:
   - Platform detected: `Generic / Web Chat`
   - Messages count: `52`
   - Code blocks and tables counted.
4. Click **Save as Markdown (.md)**:
   - Check the downloaded `.md` file in Notepad or VS Code. Notice the preserved Python code blocks and Markdown tables.
5. Click **Save as PDF**:
   - The print preview window opens automatically with styling and vector rendering.

---

## Acceptance Criteria Checklist

- [x] Works on at least 2 AI chat websites (ChatGPT and Claude DOM selectors implemented, plus generic testbed).
- [x] Save full chat or selectively chosen messages.
- [x] Headings, lists, tables, and code blocks preserved intact.
- [x] Export to both Markdown and PDF supported.
- [x] File named dynamically from chat title.
- [x] Verified with 52-message conversation testbed.
- [x] 100% offline autonomy: zero network requests.
