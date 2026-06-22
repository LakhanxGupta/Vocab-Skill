# Vocab Skill for Claude Code

A custom Claude Code skill that explains words, phrases, or sentences from your clipboard in plain, simple language — and optionally saves them to your Obsidian vault.

## What it does

Invoke `/vocab` at any point while using Claude Code. The skill will:

1. Read whatever text is currently on your clipboard
2. Explain its meaning in simple, everyday language (no jargon)
3. Give a short example of the concept in use
4. Offer to save the entry to your Obsidian vocab file

If you say yes to saving, it appends a new row to a Markdown table in your Obsidian vault at the path configured in `skill.md`.

## Installation

1. Copy `skill.md` into your Claude Code skills directory:

   ```
   ~/.claude/skills/vocab/SKILL.md
   ```

2. Update the Obsidian file path inside `skill.md` to match your vault location.

3. Restart Claude Code (or reload skills). The `/vocab` command will now be available.

## Usage

1. Copy any word, phrase, or sentence to your clipboard.
2. In Claude Code, type `/vocab`.
3. Claude reads your clipboard, explains it simply, and asks if you want to save it.

## Output format

Entries are saved as rows in a Markdown table:

| Word / Phrase | Simple Meaning | Example |
| --- | --- | --- |
| paradigm shift | A big change in the way people think about something | The internet caused a paradigm shift in how we communicate. |

## Requirements

- macOS (uses `pbpaste` to read the clipboard)
- [Claude Code](https://claude.ai/code)
- An Obsidian vault (optional — only needed if you want to save entries)
