---
description: Install the full AI website builder stack (UI/UX Pro Max + 21st.dev Magic MCP)
argument-hint:
---

# Website Builder Setup

Launch the complete installation and configuration workflow for the AI website builder stack.

## Context

This command orchestrates the installation of two complementary tools to turn
Claude Code into a professional website creation assistant:
- **UI/UX Pro Max**: design intelligence skill (styles, palettes, fonts, UX guidelines)
- **21st.dev Magic**: MCP server for high-quality AI-generated UI components

## Instructions

1. Activate the `website-builder-setup` skill and follow its workflow completely.
2. Start with Step 0 (prerequisite checks).
3. Follow steps sequentially: 0 -> 1 -> 2 -> 3.
4. Do NOT skip steps even if the user asks to.
5. For Step 2 (21st.dev), the user MUST provide their own API key — do not try to automate it.
6. End with the final summary table showing the status of each component.

## Notes

- This command is idempotent: it detects what is already installed and skips it
- The 21st.dev API key is personal and cannot be automated
- The user must have Claude Code and Node.js/npx installed
