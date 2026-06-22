---
name: vocab
description: Reads a word, phrase, or sentence directly from the system clipboard, explains its full overall meaning in extremely simple terms, and offers to save it to the Obsidian vocab file.
---

When the user invokes this skill (e.g., by typing `/vocab` without any arguments), follow these exact steps:

1. **Read the Clipboard:** Use your terminal execution tool to silently read the user's current system clipboard to get the target text. 
   - run `pbpaste`

2. **Analyze the Full Text:** Look at the exact text you retrieved from the clipboard.
   - If it is a whole sentence or phrase, explain the overall meaning of the *entire phrase together*. Do not just pick out one complex word to define.
   - If it is a single word, explain that word.

3. **Provide an Simple Explanation:**
   - Explain the meaning in plain, extremely simple, conversational language (as if explaining it to a beginner). Avoid using dictionary-style jargon or complex vocabulary in your explanation.
   - Provide one short, everyday example to show how the concept is used.

4. **Ask for Confirmation:** After providing the explanation, stop and ask the user: *"Would you like me to save this to your Obsidian Vocab file?"*

5. **Execute the Save (Table Format):** 
   - If the user says "yes", read the existing file located at: `/Users/lakhan/Library/Mobile Documents/iCloud~md~obsidian/Documents/Lakhan Gupta 2nd brain/Notes/Vocab.md`
   - If the file is completely empty or does not contain a table header, initialize it with this exact header first:
   ```markdown
     | Word / Phrase | Simple Meaning | Example |
     | --- | --- | --- |
     ```
   - Format the new entry as a single clean markdown table row:
     `| [Clipboard Text] | [Simple Meaning text, single paragraph, no newlines] | [Example text, single paragraph, no newlines] |`
   - Append this new row cleanly to the bottom of the table in the file. Ensure you strip out any inner line breaks (`\n`) from the meaning or example text so the Markdown table structure does not break.
   - If the user says "no", acknowledge and end the task without saving.
