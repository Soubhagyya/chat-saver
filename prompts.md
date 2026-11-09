# Engineering Prompts Log — Project 12: Chat Saver

This document records the step-by-step engineering prompts and design decisions used to build the Chat Saver Chrome Extension (Manifest V3).

---

### Prompt 1: Extension Architecture & Manifest V3 Configuration
> "Create a 100% offline Chrome Extension (Manifest V3) called Chat Saver. It needs to scrape active AI chat pages, preserve formatting (code blocks with syntax highlighting, tables, headings, lists), allow selective or full export, and generate both Markdown (.md) and PDF formats. Author: Soubhagyya."

*Outcome:*
- Created `manifest.json` configured with activeTab and storage permissions.
- Generated solid PNG icons (16, 48, 128px) programmatically.

---

### Prompt 2: Content Parser for Multi-Platform Chat Formats
> "Write `content.js` capable of extracting chats from ChatGPT, Claude, and generic conversation DOM trees. Parse DOM nodes into clean Markdown preserving code language tags (e.g. ```python), converting HTML tables into GFM Markdown tables (| Col 1 | Col 2 |), and retaining headers and lists without mangling."

*Outcome:*
- Engineered recursive DOM parser with specialized rules for `<pre><code>`, `<table>`, `<blockquote>`, headings, and lists.
- Built automatic chat title extractor with filesystem-safe sanitization.

---

### Prompt 3: Popup Interface & Selective Export Control
> "Build `popup.html`, `popup.css`, and `popup.js` displaying conversation metrics (message count, code blocks, tables). Add a toggle between 'All Messages' and 'Selective', with individual message checkboxes. Add two primary actions: 'Save as Markdown' and 'Save as PDF'."

*Outcome:*
- Interactive popup showing instant conversation statistics.
- Selective drawer allowing precision filtering of message turns before downloading.

---

### Prompt 4: Clean Markdown Generator & Print-to-PDF Engine
> "Implement client-side export routines in `popup.js`. Markdown export must use standard GFM formatting with conversation metadata headers. PDF export must open a clean, print-styled HTML preview that automatically launches Chrome's native vector Print-to-PDF dialog."

*Outcome:*
- High-fidelity Markdown generator with zero remote server requirements.
- Print-optimized CSS layout producing clean multi-page PDFs with intact tables and code blocks.

---

### Prompt 5: Large Offline Conversation Verification Fixture
> "Create an offline test fixture containing 50+ messages with Python code snippets, comparison tables, and user/assistant dialogue turns to verify compliance with the 50-message acceptance criterion without needing internet or paid accounts."

*Outcome:*
- Built `sample_chat_50_messages.html` containing 52 simulated turns.
- Verified that all 52 turns, Python hash ring code, and SQL vs NoSQL tables export flawlessly.
